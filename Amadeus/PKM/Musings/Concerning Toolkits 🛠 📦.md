---
Note Type: "Literature"
Author: "Kent C. Dodds"
Primary Zettelkasten Area: "Tooling"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 25, 2022 8:27 PM"
Sources: "Concerning Toolkits"
---

# Concerning Toolkits 🛠 📦

Could I create a proper tool that bootstrapped me everything regarding app infrastructure with common up to date tooling?

I wonder If I should try to wrap everything on my abstraction or attempt to serve as a scaffolder. I guess the latter is easier and then I can pivot to something bigger.

The key pieces would be the framework of the concern in addition to the AWS infrastructure.

```bash
# Generate static website project.
$ avalon new static-website

# Generate next project (Tailwind).
$ avalon new dynamic-website

# Generate api project.
$ avalon new http-api

# Generate Typescript project.
$ avalon new library
```

[https://twitter.com/kentcdodds/status/941330985836208128](https://twitter.com/kentcdodds/status/941330985836208128)

> *Toolkits are "a set of tools in any form that allows you to create applications with no build configuration." (via [Ronald Rey](https://twitter.com/reyronald) in [awesome-toolkits](https://github.com/reyronald/awesome-toolkits)). For a few examples: [react-scripts](https://github.com/facebook/create-react-app/tree/master/packages/react-scripts) (what [create-react-app](https://github.com/facebook/create-react-app) leaves you with), my own [paypal-scripts/kcd-scripts](https://kentcdodds.com/blog/tools-without-config), [parcel](https://github.com/parcel-bundler/parcel), [preact-cli](https://github.com/developit/preact-cli), [ember-cli](https://ember-cli.com/) (the first widely used toolkit for JS), and [many more](https://github.com/reyronald/awesome-toolkits).*
> 

> *The idea behind these tools is it allows you to install a single dependency in your project which normally includes a CLI you can use to run scripts for your projects. They generally will use tools under the hood to accomplish their job. Some toolkits are focused on a specific part of your project's needs (like parcel or preact-cli which focus on the build) while other tools cover much more (like react-scripts which also covers testing and my scripts projects which cover a TON of stuff like prettier auto-formatting, releasing, etc). The goal is that they cover as many use cases as possible without requiring any configuration, and in many cases allow for some additional configuration to cover more use cases.*
> 

> *Owning a car and learning to drive it is nice, but if you can get around without worrying about it, then a whole category of problems can go away (like pushing maintenance of the vehicle off to someone else). It's a bit of a loose analogy, but maybe it'll help a bit with understanding the role that toolkits can play.*
> 

> ***Toolkits don't try to handle the 10000 of use cases in the world. Instead, they use underlying tools and some glue to put together a single tool that can handle as many use cases as possible without complicating the tool too much or requiring config.** If your use case is a special snowflake, then you do have a recourse available. With `react-scripts` you can [eject](https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md#npm-run-eject). With most other tools however, you have another option...*
> 

> *And just to drive the point home a little further... Most devs using these kinds of tools don't know or care how they work or are configured. They just want to ship stuff. I really appreciated the perspective [TJ Holowaychuk](https://twitter.com/tjholowaychuk) [gave](https://twitter.com/tjholowaychuk/status/941361591861223424) in the thread:*
>