---
Note Type: "Literature"
Author: "Mark Erikson"
Primary Zettelkasten Area: "Front-End Development"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Software Architecture"
Status: "Processed"
Created time: "October 18, 2022 2:50 AM"
Sources: "Thoughts On React Hooks, Redux And Separation Of Concerns"
---

# Thoughts On React Hooks, Redux and Separation Of Concerns

- The react community has goes too crazy on new things. Labeling as hooks the "*obvious way*" to write components.
- In one side nothing has really changed in the sense that hooks just let you do the same thing as class based components.
- In another side, hooks allows developers to co-locate logic that was spread in different lifecycles methods but this requires knowledge in closures instead of “this”.
- The collocation that hooks allows is good but complex components can get very large. You can treat some of the size problems with techniques like extracting into custom hooks but having to define functions inline takes too much space inside the component and does not make much sense outside the component.
- HOCS:
    - Promote writing simple components that receive props, which makes them decoupled and reusable.
    - Cons: Extra layers and indirection with possible name clashing.
- Hooks:
    - Allow for smaller component trees, logic extraction and just using functions.
    - Strong coupling with dependencies
- The redux team promotes having components that are unaware of redux, which is just having coupled components ([https://react-redux.js.org/introduction/why-use-react-redux#it-encourages-good-react-architecture](https://react-redux.js.org/introduction/why-use-react-redux#it-encourages-good-react-architecture)).
- Side effects should be part of the action creation process and not inside components ([https://redux.js.org/faq/actions#how-can-i-represent-side-effects-such-as-ajax-calls-why-do-we-need-things-like-action-creators-thunks-and-middleware-to-do-async-behavior](https://redux.js.org/faq/actions#how-can-i-represent-side-effects-such-as-ajax-calls-why-do-we-need-things-like-action-creators-thunks-and-middleware-to-do-async-behavior)).
- Coupling is not a problem of redux but of hooks. Redux made some decisions that imply some coupling but now with hooks the coupling feels way stronger. There is "*an implicit dependency of the context and the data being provided*".
- The questions around hooks may be related to the different react mindsets: "app-centric" vs "component-centric" design [https://twitter.com/acemarke/status/1056669495354421249](https://twitter.com/acemarke/status/1056669495354421249).