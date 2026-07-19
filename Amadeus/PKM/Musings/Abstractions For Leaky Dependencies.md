---
Note Type: "Literature"
Author: "Sarah Dayan"
Primary Zettelkasten Area: "Software Architecture"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Unprocessed"
Created time: "October 18, 2022 12:58 AM"
Sources: "Wrapping Dependencies Into Custom Abstractions"
---

# Abstractions For Leaky Dependencies

> One of my favorite software development practices is to wrap dependencies into custom abstractions.
I hate it when a third-party leaks all over my code and a refactor takes hours (if not days) because of it.

Instead, isolate that dependency in a custom module (ideally, inject it for easier testing) and use that module in your code.
This decouples the code and simplifies refactors. Change it in the wrapper, make sure you respect the interface, and it all flows through your app.

A good example is an HTTP client. If you import it "bare bones" everywhere you need it, good luck when you decide to swap it with something better suited for your needs.
Remember, what you need on day one is most likely going to change as your application grows.

If you let a dependency "invade" your code, you're inevitably going to couple your entire application to it.
This means you will make choices that lean towards making the library happy, and end up with code which requires a significant cognitive overhead.

Ideally, when you change something in your app, you should only be concerned with the necessary knowledge of changing that thing.
If you also need to understand 25 custom libraries to wrap your head around it, that's most probably a code smell.

In the OOP world, this is known as the bridge pattern. The goal is to "decouple an abstraction from its implementation so that the two can vary independently".
Even though this is usually presented with classical inheritance, you can make a bridge with function composition.

So, concretely, imagine you're working on an application that uses the native Fetch API. You made that choice a while ago because that was enough, but your application is growing, you need to cover more use cases, and you decide that it's time to move to something like Axios.

If you've leaked your usage of Fetch everywhere, you're in for a nasty refactor. Not only are you changing an implementation, but now you must also go over every single place where you've ever used it.

A targeted, focused change is now having a domino effect on the entire app.

If you've wrapped Fetch in an abstraction that makes sense for your app (e.g., a simple function), then you've isolated its usage. You've pre-filled it with sensible defaults, and specialized it into a module that anyone with domain knowledge of your app can understand.

And you can keep on wrapping these abstractions to make specialized ones.
Fetch -> dataStore -> books -> allBooks -> allBooksByYear -> ...

If I'm new to your app, and I see an object called `api` or `dataStore`, it's much simpler for me to wrap my head around it than any exotic library that I may have never heard of.
Instead, I see consistent naming patterns, consistent interface choices, and I'm focused on domain.

If you inject the dependency, you get an extra bonus when testing. No weird, long, coupled mocks. All you have to do is inject a test double in a way that respects the interface of your abstraction.
Changing the underlying implementation shouldn't change your tests.
> 

[https://twitter.com/frontstuff_io/status/1264189583220244480?s=20](https://twitter.com/frontstuff_io/status/1264189583220244480?s=20)

[https://twitter.com/frontstuff_io/status/1264189585917120517](https://twitter.com/frontstuff_io/status/1264189585917120517)

[https://twitter.com/frontstuff_io/status/1264189588270125057?s=20](https://twitter.com/frontstuff_io/status/1264189588270125057?s=20)

[https://twitter.com/frontstuff_io/status/1264189590686126080?s=20](https://twitter.com/frontstuff_io/status/1264189590686126080?s=20)

[https://twitter.com/frontstuff_io/status/1264189593286586368?s=20](https://twitter.com/frontstuff_io/status/1264189593286586368?s=20)

[https://twitter.com/frontstuff_io/status/1264189595157237760?s=20](https://twitter.com/frontstuff_io/status/1264189595157237760?s=20)

[https://twitter.com/frontstuff_io/status/1264189597153669121?s=20](https://twitter.com/frontstuff_io/status/1264189597153669121?s=20)

[https://twitter.com/frontstuff_io/status/1264189599628353538?s=20](https://twitter.com/frontstuff_io/status/1264189599628353538?s=20)

[https://twitter.com/frontstuff_io/status/1264189602245509121?s=20](https://twitter.com/frontstuff_io/status/1264189602245509121?s=20)

[https://twitter.com/frontstuff_io/status/1264189604959223809?s=20](https://twitter.com/frontstuff_io/status/1264189604959223809?s=20)

[https://twitter.com/frontstuff_io/status/1264189607379447808?s=20](https://twitter.com/frontstuff_io/status/1264189607379447808?s=20)

[https://twitter.com/frontstuff_io/status/1264189610000875520?s=20](https://twitter.com/frontstuff_io/status/1264189610000875520?s=20)