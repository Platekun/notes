---
URL: "https://www.epicweb.dev/the-webs-next-transition"
---

# The Web’s Next Transition | Epic Web Dev by Kent C. Dodds

[](The%20Web%E2%80%99s%20Next%20Transition%20Epic%20Web%20Dev%20by%20Kent%20C%20D/image)

The web is made up of technologies that got their start over 25 years ago. HTTP, HTML, CSS, and JS were all first standardized in the mid-nineties (when I was 8 years old). Since then, the web evolved into a ubiquitous application platform. As the web has evolved, so too has the architecture for the development of these applications. There are many core architectures for building applications for the web these days. The most popular architecture employed by web developers today is the Single Page App (SPA), but **we are transitioning** to a *new and improved* architecture for building web applications.

The `<a>` and `<form>` elements have been around from the very beginning. Links for a browser to get things from a server, and forms for a browser to send things to a server (and get things in return). With this two-way communication established as a part of the specification from the start, it has been possible to create powerful applications on the web forever.

Here are the major architectures (in chronological order of popular use):

1. Multi-Page Apps (MPAs)
2. Progressively Enhanced Multi-Page Apps (PEMPAs, aka “JavaScript Sprinkles”)
3. Single Page Apps (SPAs)
4. *The next transition*

Each architecture of web development has benefits and pain points. Eventually, the pain points became enough of a problem to motivate the move to the next architecture which came with its own trade-offs.

No matter how we build our applications, we’re almost always going to need code running on a server (notable exceptions includes games like Wordle which [*used to*] store game state in local storage). One of the things that distinguishes these architectures is *where the code lives.* Let’s explore each of these in turn and watch how the location of code changed over time. As we cover each architecture, we’ll consider specifically the following use cases of code:

- Persistence - saving and reading data from a database
- Routing - directing traffic based on the URL
- Data fetching - retrieving data from persistence
- Data mutation - changing data in persistence
- Rendering logic - displaying data to the user
- UI Feedback - responding to user interaction

There are, naturally, more parts of a web application than these bits, but these are the bits that move around the most and where we spend the bulk of our time as web devs. Depending on project scale and team structure we may work in all of these categories of code or we may work on only a part of one.

## Multi-Page Apps (MPAs)

In the early days, this is the only architecture that worked at all on the web based on the capabilities of web browsers at the time.

With Multi-Page Apps, all of the code we write lives on the server. The UI Feedback code on the client is handled by the user’s browser.

### GET and POST Requests

**GET Requests:** When the user enters a URL in the address bar, the browser sends a request to our server. Our routing logic will call a function to fetch data which communicates with the persistence code to retrieve the data. This data then gets used by the rendering logic to determine the HTML which will be sent as a response to the client. All the while, the browser is giving the user feedback with some kind of pending state (normally in the favicon position).

**POST Requests:** When the user submits a form, the browser serializes the form into a request sent to our server. Our routing logic will call a function to mutate the data which communicates with the persistence code to make the database updates. Then it will respond with a redirect so the browser triggers a GET request to get fresh UI (which will trigger the same thing that happened when the user entered the URL to begin with). Again, the browser will give the user feedback with pending UI.

### Pros and cons

The mental model of MPAs is simple. We didn’t appreciate it back then. While there was *some* state and complicated flows handled primarily by cookies in the requests, for the most part everything happened within the time of a request/response cycle.

Where this architecture falls short:

1. Full-page refreshes - Makes some things hard (focus management), other things impractical (imagine a full-page refresh every time we liked a tweet…), and some things just impossible (animated page transitions).
2. UI Feedback control - It’s nice that the favicon turns into a spinner, but often a better UX is feedback that is visually closer to the UI the user interacted with. And it’s certainly something designers like to customize for branding purposes. And what about optimistic UI?

It’s notable that the web platform is constantly improving with [the upcoming page transitions API](https://developer.chrome.com/blog/shared-element-transitions-for-spas/) which makes MPAs a more viable option for more use cases. But for the majority of web applications, that’s still not enough. In any case, at the time this problem was far from the minds of standards committees and our users wanted more now!

## Progressively Enhanced Multi-Page Apps (PEMPAs)

Progressive Enhancement is the idea that our web applications should be functional and accessible to all web browsers and then leverage whatever extra capabilities the browser has to enhance the experience. The [term was coined in 2003](https://www.hesketh.com/publications/progressive_enhancement_and_the_future_of_web_design.html) by Nick Finck and Steve Champeon. Speaking of the capabilities of the browser…

XMLHttpRequest was initially developed by Microsoft’s Outlook Web Access team in 1998 but it wasn’t [standardized](https://www.w3.org/TR/XMLHttpRequest/) until 2016 (can you believe that!?). Of course that never stopped browser vendors and web devs before. AJAX was popularized as a term in 2005 and a lot of people started making HTTP requests in the browser. Businesses were built on the idea that we don’t have to go back to the server for any more than little bits of data to update the UI in place. With that, we could build Progressively Enhanced Multi-Page Apps:

“Whoa!” you might be thinking, “wait a minute… where’d all this code come from?” So now we’ve not only taken responsibility of UI feedback from the browser, we also have Routing, Data fetching, Data mutation, and Rendering logic to the client *in addition* to what we already had on the server. “What gives?”

Well, here’s the deal. The idea behind progressive enhancement is that our baseline should be a functional app. Especially in the early 2000s, we couldn’t guarantee that our user would be using a browser capable of running our fancy new AJAX stuff, or that they would be on a fast enough network to download our JavaScript before interacting with our app. So we needed to keep the existing MPA architecture in place and only use JavaScript to *enhance* the experience.

That said, depending on the level of enhancement we’re talking about, we may indeed have to write code in almost all of our categories, persistence being the exception (unless we want offline mode support which is really neat, but not an industry standard practice, so it’s not included in the chart). This is the era of jQuery, MooTools, etc.

### GET and POST requests

Note: When the user requests the document for the first time, the same thing happens here as it does in the MPA example. However, when the user clicks a link to another page or submits a form, things change. Additionally, PEMPAs will include `<script>` tags which will be used for the enhancement capabilities.

Also note that while other request methods are possible here, if we rely on them we risk breaking progressive enhancement because the `method` attribute of `<form>` only supports `get` and `post`. That’s why we’re only talking about GET and POST. We can absolutely delete a record by POSTing it’s ID 😉

**GET Requests:** When the user clicks an anchor element with an `href` that is within our app, our client-side data fetching code prevents the default full-page refresh behavior and uses JavaScript to update the URL. Then the client routing logic determines what updates need to happen to the UI and manually performs those updates, including displaying any pending states while the data fetching library makes a network request to a server endpoint. The server routing logic calls the data fetching code to retrieve data from the persistence code and sends that as a response (as XML or JSON, we get to choose 😂) which the client then uses to perform the final UI updates with its rendering logic.

**POST Requests:** When the user submits a form, our client-side data mutation logic prevents the default full-page refresh and post behavior and uses JavaScript to serialize the form and send the data to a server endpoint. The server routing logic then calls the data mutation function which interacts with the persistence code to perform the mutation and responds with the updated data to the client. The client rendering logic will use that updated data to update the UI however is needed, in some cases the client-side routing logic will send the user to another place.

### Pros and cons

We definitely solved the problems with MPAs by bringing along client-side code and taking the UI Feedback responsibility onto ourselves. We have much more control and can give users a more custom app-like feel.

Unfortunately, to give the users the best experience they’re looking for we have to be responsible for routing, data fetching, mutations, and rendering logic. There are a few problems with this:

1. We don’t do as good a job as the browser does with routing and form submission. Keeping the data on the page up-to-date was never a concern before, but now it’s over half of our client-side code. Also, race conditions, form resubmissions, and error handling are great places for bugs to hide.
2. There’s a lot more code to manage that we didn’t have to write before. I know correlation does not imply causation, but I’ve noticed that in general the more code we have, the more bugs we have 🤷‍♂️
3. There is a *lot* of code duplication with regards to rendering logic. The client code needs to update the UI in the same way the backend code would render every possible state after a mutation or client transition. So the same UI that the backend has must be available in the frontend as well. And most of the time these are in completely different languages which makes code sharing a non-starter. And it’s not just the templates, but also the logic. The challenge is: “make a client-side interaction, then make sure the UI updated by the client code is the same as what would have happened if it had been a full-page refresh.” This is surprisingly difficult to do (there’s [a site](https://github.com/) us developers use on a regular basis that is a PEMPA and very frequently does not do this correctly).
4. Code organization with PEMPAs is very difficult. With no centralized place to store data or render UI, people were manually updating the DOM just about anywhere and it was very difficult to follow the code which slowed down development.
5. There’s indirection between the API routes and the client-side data fetching and data mutation code that uses them. A change on one side of the network necessitates a change on the other side and that indirection made it difficult to know we haven’t broken anything because following code paths involved wading through a series of files. The network became a barrier that caused this indirection in the same way a fox uses a river to throw off the hound’s scent.

On a personal note, this is around the time I entered the web development world. I recall this time with a mix of longing nostalgia and shivery fright 🍝.

## Single Page Apps (SPAs)

It didn’t take long before we realized we could remove the duplication problems if we just deleted the UI code from the backend. So that’s what we did:

You’ll notice this graphic is almost identical to the PEMPA one. The only difference is the Rendering logic is gone. Some of the routing code is gone as well because we no longer need to have routes for UI. All we’re left with is API routes. This is the era of Backbone, Knockout, Angular, Ember, React, Vue, Svelte, etc. This is the strategy used by **most** of the industry today.

### GET and POST requests

Because the backend no longer has rendering logic, all document requests (the first request a user makes when they enter our URL) are served by a static file server (normally a CDN). In the early days of SPAs, that HTML document was almost always an effectively empty HTML file with a `<div id="root"></div>` in the `<body>` which would be used to “mount” the application. These days, however, frameworks allow us to pre-render as much of the page as we know at build-time using a technique known as “Static Site Generation” (SSG).

The GET and POST requests in this strategy are the same as they are with PEMPAs. Only now we mostly use `fetch` instead of `XHRHttpRequest`.

### Pros and cons

By far the biggest pro here is the developer experience. That was the original driving force for the transition from PEMPAs to SPAs in the first place. Not having code duplication was an enormous benefit. Unfortunately that’s about all that SPAs solved. I remember personally being convinced that SPA architecture helped with perceived performance because a CDN could respond with an HTML document faster than a server could generate one, but in real world scenarios that never seemed to make a difference. The sad reality is that SPAs still have all the same other issues as PEMPAs, albeit with more modern tools that make things much easier to deal with.

To make matters worse, SPAs also introduced several new problems:

1. Bundle size explosion. Read more about JavaScript’s impact on a web page’s performance in [this thorough article on the Web Almanac](https://almanac.httparchive.org/en/2022/javascript).
2. Waterfalls. Because all the code for fetching data now lives within the JavaScript bundle, we have to wait for that to be downloaded before we can fetch the data. Compounded with this is the need to leverage code splitting and lazy-loading of these bundles and now we have critical dependency situation like this: `document` → `app.js` → `page.js` → `component.js` → `data.json` → `image.png`. This is not great and ultimately results in a *much* worse user experience. For static content we can avoid much of this, but there are a whole host of issues and limitations with that which the purveyors of SSG strategies are working on and are happy to sell us their vendor-specific solutions to.
3. Runtime performance. With so much client-side JavaScript to run, some lower-powered devices struggle to keep up (Read: [The Cost of JavaScript](https://v8.dev/blog/cost-of-javascript-2019)). What used to run on our beefy servers is now expected to run on people’s mini-computer in their hand. I know we sent people to the moon with less power, but still this is a problem.
4. State management became a huge problem. Before, the MPA would render our state in the DOM and we’d just reference/mutate that. Now we’re just getting JSON and we have to not only let the backend know when data has been updated, but keep the in-memory representation of that state up-to-date. This has all the marks of the challenges of caching, which is one of the hardest problems in software. In a typical SPA, state management represents 30-50% of the code people work on.

Libraries have been created to help wrangle these issues and reduce their impact. This has been incredibly helpful, but some would call the churn [fatiguing](https://medium.com/@ericclemmons/javascript-fatigue-48d4011b6fc4). This has become the de-facto standard way to build web apps since the mid-2010s. We’re well into the 2020s and there are some new ideas on the horizon.

## Progressively Enhanced Single Page Apps (PESPAs)

MPAs have a simple mental model. SPAs have more powerful capabilities. Folks who have been through the MPA stage and are working in SPAs truly lament the simplicity we’ve lost in the last decade. This is particularly interesting if you consider the fact that the motivation behind the SPA architecture was primarily for improving the developer experience over PEMPAs. If we could somehow merge SPAs and MPAs into a single architecture to get the best of both, then hopefully we’ll have something that is both simple and more capable. That’s what Progressively Enhanced Single Page Apps are.

Consider that with Progressive Enhancement the baseline is a functional app, even without client-side JavaScript. So if our framework enables and encourages Progressive Enhancement as a core principle, then the foundation of our app comes with the solid foundation of the simple mental model of MPAs. Specifically, the mental model of thinking of things in the context of a request/response cycle. This allows us to largely eliminate the problems of SPAs.

In order to do this, PESPAs need to “emulate the browser” when they prevent default. So the server code works the same way regardless of whether the browser is making the request or a JavaScript-based fetch request is being made. So while we do still own that code, we can keep the simple mental model in the rest of our code. An important part of this is that PESPAs emulate the browser’s behavior of revalidating data on the page when mutations are made to keep the data on the page up-to-date. With MPAs, we just got a full-page reload. With PESPAs, this revalidation happens with fetch requests.

Remember we had one significant problem with PEMPAs as well: code duplication. PESPAs solve this problem by making the backend UI code and frontend UI code *the exact same*. By using a UI library capable of both rendering on the server and becoming interactive/handling updates on the client, then we don’t have code duplication issues.

You’ll notice there are small boxes for data fetching, mutation, and rendering. These bits are for enhancement. For example, pending states, optimistic UI, etc. don’t really have a place on the server, so we’re going to have some code that’s run only on the client. But even with that, with modern UI libraries the colocation we get makes it tenable.

### GET and POST requests

Document requests with PESPAs are effectively identical to PEMPAs. The initial HTML needed for the app is sent straight from the server and JavaScript is also loaded to enhance the experience for user interactions.

**GET Requests:** When the user clicks a link, we’ll prevent the default behavior. Our router will determine the data and UI needed for the new route and trigger data fetching for whatever data the next route needs and render the UI that’s rendered for that route.

**POST Requests:** Mutations with PESPAs are done via form submissions. No more of this `onClick` + `fetch` nonsense (however, imperative mutations are fine for progressive enhancement like redirecting to the login screen when the user’s session times out). When the user submits a form, we’ll prevent the default behavior. Our mutation code serializes the form and sends it as a request to the route associated to the `action` of the form (which defaults to the current URL). The routing logic on the backend calls the action code which communicates with the persistence code to perform the update and sends back a successful response (for example: a tweet like) or redirect (for example: creating a new GitHub repo). If it’s a redirect, the router loads code/data/assets for that route (in parallel) and then triggers the rendering logic. If it’s not a redirect, the router revalidates the data for the current UI and triggers the rendering logic to update the UI.

### Pros and cons

PESPAs eliminate a ton of problems from previous strategies. Let’s look at them one by one:

MPA Issues:

1. Full-page refreshes - PESPAs prevent default behavior and instead use client-side JS to emulate the browser. From the perspective of the code we write, this doesn’t feel any different from an MPA, but from the perspective of the user, it’s a much improved experience.
2. UI Feedback control - PESPAs allow us to completely control the network requests because we’re preventing default and making fetch requests and we can therefore provide users with feedback in whatever way makes the most sense for our UI.

PEMPA Issues:

1. Prevent default to a worse experience - A core aspect of PESPAs is they should behave in much the same way the browser does with regard to routing and forms. This is how they accomplish giving us the mental model of an MPA. Cancelling requests from form resubmissions, handling out-of-order responses properly to avoid race condition issues, and surfacing errors to avoid spinners that never go away are all part of what makes a PESPA a PESPA. This is where a framework really helps out.
2. Amount of custom code - By sharing code between the client and server and having the right abstractions that emulate browser behavior, we end up drastically reducing the amount of code we have to write ourselves.
3. Code duplication - Part of the idea of a PESPA is that the server and client use the *exact same* code for rendering logic. So there is no duplication to speak of. Don’t forget the challeng: “make a client-side interaction, then make sure the UI updated by the client is the same as what we get if we refresh the page.” With a PESPA it should always pass without effort or consideration on the part of us developers.
4. Code organization - Because of the mental model offered by the PESPAs’ browser emulation, application state management is not a consideration. And rendering logic is handled the same on both sides of the network so there are no haphazard DOM mutations either.
5. Server/Client indirection - The PESPA emulating the browser means that the code for the frontend and the code for the backend are colocated which eliminates the indirection and makes us much more productive.

SPA Issues:

1. Bundle size - Going to a PESPA requires a server which means we can move a **ton** of our code to the backend. All the UI needs is a small UI library that can run both on the server and client, some code for handling UI interactions and feedback, and the code for the components. And thanks to the URL (route-based) code splitting we can finally say goodbye to web pages with hundreds of KBs of JS. On top of this, because of progressive enhancement, *most* of the app should work *before* the JS is finished loading anyway. On top of this, there are efforts right now in JS frameworks to further shrink the amount of JS needed in the client.
2. Waterfalls - An important part of PESPAs is that they can be aware of code, data, and asset requirements for a given URL without having to run any of the code. This means that in addition to code-splitting, PESPAs can trigger a fetch for code, data, and assets all at once instead of waiting for one at a time in series. This also means that PESPAs can pre-fetch these things **before** the user triggers a navigation so that when they’re required the browser can turn around and hand them back immediately, making the entire experience of using the app feel instant.
3. Runtime performance - PESPAs have two things going for them in this department: 1) they move a lot of code to the server so there’s less code for devices to execute in the first place and 2) thanks to Progressive Enhancement, the UI is ready to use before the JS is finished loading and executing.
4. State management - Because of browser emulation which gives us the MPA mental model, application state management just isn’t a concern in a PESPA context. The evidence of this is the fact that the app should mostly work without JavaScript at all. PESPAs automatically revalidate the data on the page when mutations are complete (MPAs got that for free thanks to a full-page reload).

It’s important to call out that PESPAs will not work exactly the same with and without client-side JavaScript. That’s never the goal of progressive enhancement anyway. Just that most of the app should work without JavaScript. And it’s not just because we care about the sans-JavaScript user experience. It’s because by targeting progressive enhancement, we drastically simplify our UI code. You’d be surprised how far we can get without JS, but for some applications it’s just not necessary or practical to have everything work without client-side JavaScript. But we still can reap the primary benefits of PESPAs even if some of our UI elements do require some JavaScript to operate.

What distinguishes a PESPA:

- Functional is the baseline - JS used to enhance not enable
- Lazy loading + intelligent pre-fetching (more than just JS code)
- Pushes code to the server
- No manual duplication of UI code (as in PEMPAs)
- Transparent browser emulation (#useThePlatform)

As for the cons. We’re still discovering what those are.

Many who are used to SPAs and SSG will lament that we now have server-side code running our app. However for any real-world app we can’t avoid server-side code. There are certainly *some* use cases where we can build the entire site once and stick it on a CDN, but most apps we work on for our day jobs don’t fit into this category.

Related to this is people are concerned about server cost. The idea is that SSG allows us to build our app once and then serve it via a CDN to an almost infinite number of users at very low cost. There are two flaws with this criticism. 1) We’re probably hitting APIs in our app, so those users will still be triggering plenty of our most expensive server-side code on their visits anyway. 2) CDNs support HTTP caching mechanisms, so if we’re really able to use SSG, then we can definitely make use of that to give both fast responses and limit the amount of work our rendering server is dealing with.

Another common issue people have with leaving SPAs is that now we have to deal with the challenges of rendering on the server. This is definitely a different model for folks used to running their code only on the client, but if we’re using tools that have taken this into consideration, it’s hardly a challenge. If we’re not, then it can definitely be a challenge, but there are reasonable workarounds to force certain code to only run client-side while we migrate.

As I said, we’re still discovering the cons of Progressively Enhanced Single Page Apps, but I think the benefits are worth the trade-offs we can perceive so far.

## A PESPA Implementation: Remix

Leading the charge for PESPAs is [Remix](https://remix.run/), a web framework with a laser focus on web fundamentals and modern user experience. Remix is the first web framework to out of the box offer everything that I described a PESPA offering. Other frameworks can and are adapting to follow Remix’s lead on this. I’m specifically aware of both [SvelteKit](https://github.com/sveltejs/kit/discussions/5875) and [SolidStart](https://github.com/solidjs/solid-start/pull/74) working in PESPA principles into their implementations. I imagine more will follow. Here’s how things look when we’ve got a web framework for our PESPA:

In this case, Remix acts as a bridge across the network. Without Remix, we’d have to implement this ourselves to have a complete PESPA. Remix also handles our routing via a combination of convention-based and config based routing. Remix will also help with the progressively enhanced bits of our data fetching and mutations (like the twitter like button) and the UI feedback for implementing things like pending states and optimistic UI.

Thanks to the nested routing built into Remix, we get better code organization as well (something Next.js is pursuing as well). While nested routing isn’t required for the PESPA architecture specifically, route-based code splitting is an important part. Also, we get much more granular code splitting with nested routing so it is an important aspect.

Remix is demonstrating that we can have more fun building better experiences faster with the PESPA architecture. And we end up with situations like this one:

A perfect perf lighthouse score without trying? Sign me up!

## Conclusion

Personally, I’m super here for this transition. Getting a better UX and DX at the same time is a solid win. I think it’s an important one and I’m excited about what the future holds for us. As a reward to you for finishing this blog post, I’ve made a repository that demonstrates all this code moving around through the ages using a TodoMVC app! Find it here: [kentcdodds/the-webs-next-transformation](https://github.com/kentcdodds/the-webs-next-transformation). Hopefully it helps make some of the ideas more concrete.

Cheers!

For a more detailed look at the history of building for the web, read [“The new wave of Javascript web frameworks”](https://frontendmastery.com/posts/the-new-wave-of-javascript-web-frameworks/) by Frontend Mastery

For more on progressive enhancement, read [Progressively enhance for a more resilient web](https://jjenzz.com/progressively-enhance-for-a-more-resilient-web) by [Jenna Smith](https://jjenzz.com/).

Written by Kent C. Dodds

Kent is a world renowned speaker, teacher, and trainer and he's actively involved in the open source community as a maintainer and contributor of hundreds of popular npm packages. He is the creator of [EpicReact.Dev](https://epicreact.dev/) and [TestingJavaScript.com](https://testingjavascript.com/).

I respect your privacy. Unsubscribe at any time.