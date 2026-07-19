---
note-type: "Literature"
author: "Carlos Lobo"
primary-zettelkasten-area: "Docker"
status: "Processed"
sources: "Unknown"
---

# What Is An Image?

Images are templates or blueprints to [[Amadeus/PKM/Musings/What Are Containers|containers]], they contain the code along with the runtime dependencies. An image can be used to create an unlimited number of [[Amadeus/PKM/Musings/What Are Containers|containers]].

They are inmutable, meaning we need cannot modify them. Once an image is built, we need to build a new image everytime we wish to run a [[Amadeus/PKM/Musings/What Are Containers|container]] with our changes.