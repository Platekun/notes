---
note-type: "Literature"
author: "Dan Abramov"
primary-zettelkasten-area: "Developer Mindset"
last-edited-time: "September 20, 2023 2:23 AM"
status: "Processed"
created-time: "October 18, 2022 12:58 AM"
sources: "URL(s) are a Lossy Representation Of The Application Navigation State (../Sources/URL(s)%20are%20a%20Lossy%20Representation%20Of%20The%20Applicati%209ef3ba5db4104cc3863a4586a6f8dd07.md)"
---

# Application States Cannot Be Entirely Serialized

Abramov thoughts are somewhat similar to [[URL(s) Represent Intent And Reconciliation]] while also adding that if you try to serialize application states yo get URL(s) but not every URL is unique.

Since URL(s) are not unique they should at least drive to a consistent initial state.

> In other words, URL is a lossy representation of the app’s navigation state.
Different navigation states may serialize into the same URL. So a URL does not uniquely represent each of them.
But each URL should lead to a single consistent navigation state on the first load.
> 

[https://twitter.com/dan_abramov/status/1258572152934215682?s=20](https://twitter.com/dan_abramov/status/1258572152934215682?s=20)