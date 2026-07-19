---
URL: "https://kentcdodds.com/blog/improving-the-usability-of-your-modules"
---

# Improving The Usability Of Your Modules

Remove side-effects from the root-level of most of your modules and give users control if they are required.

> *This presents a few challenges for users of the module. It means that **they have to be aware of what happens when they import your module**. They have to make sure that they don't import your module before the global environment is ready for it. And that problem manifests itself not only in the application environment, but also in the test environment! And unless you take care to give good warnings when the environment isn't ready (if you even know), people will get cryptic error messages when doing seemingly unrelated tasks (like importing some module that happens to import your module somewhere in the [dependency graph](https://twitter.com/kentcdodds/status/922114804038303745)).*
> 
> 
> ```jsx
> // react-i18n/index.js
> // ... stuff
> // side-effect!
> const content = JSON.parse(document.getElementById('react-messages'))
> // ... more stuff
> export {getContentForFile as default, init}
> ```
> 

> *Another issue is that there could be a reason to **configure the initialization process**. What if my node doesn't have the id `react-messages`, but instead uses `i18n-content`? Or what if I don't server-render the messages at all and they're coming from an ajax request? Turns out that `react-i18n` actually exposed another module `react-i18n/bootstrap` to customize this behavior which is great, but that doesn't resolve the problem of stuff happening if someone were to import `react-i18n` first.
So what I did was a wrapped all side-effects in a function I exported called `init`(which was similar to the `bootstrap` thing it already exported):*
> 
> 
> ```jsx
> // react-i18n/index.js
> // ... stuff
> function init(options) {
>   // ... other stuff
>   // side-effect! But it's ok now because that's clear
>   const messages = JSON.parse(document.getElementById('react-messages'))
>   // ... other other stuff
> }
> // ... more stuff
> export {getContentForFile as default, init}
> ```
> 
> *So this means that anyone using the module now must call the `init` function, but they're doing that on their own terms and whenever they want it to happen which I think is the key difference. It doesn't matter whether someone imports this module before initialization takes place. It also gives us an opportunity to give a more informative error message if they fail to initialize before they start using the module.*
> 
> ***The key is that your module shouldn't do side-effects when it's imported. Instead, export functions which perform the side-effects.** This gives the users control over when and what happens. Even better is to not have any side-effects at all if you can help it (which is actually also possible to accomplish with my reworking of `react-i18n`), but that's a subject for another newsletter.*
>