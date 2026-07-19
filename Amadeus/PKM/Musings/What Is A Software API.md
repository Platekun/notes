---
Note Type: "Literature"
Author: "Carlos Lobo"
Primary Zettelkasten Area: "Software Development"
Last edited time: "September 20, 2023 2:23 AM"
Secondary Zettelkasten Area: "Developer Mindset"
Status: "Processed"
Created time: "November 8, 2022 1:13 AM"
Sources: "Unknown"
---

# What Is A Software API?

A software API is an [[Amadeus/PKM/Musings/What Is An API|API]] that describes what the expected behavior is. The programs involved in this type of API are the programmer’s and an external one provided by a third-party (like a framework or library) or even a colleague’s.

```tsx
export interface CartInterface {
	add(): void;
	checkout(): void;
}

export interface ItemInterface {
	offerId: string;
	name: string;
}

export function createCartObject(): CartInterface {
	return {
		add(item: ItemInterface) {
			console.info("Add", item)
		},
		checkout() {
			console.info("Checkout!");
		},
	};
}
```

```tsx
import { createCartObject, CartInterface, ItemInterface } from 'library';

function buyNow(cart: CartInterface, item: ItemInterface) {
	cart.add(item);
	cart.checkout();
}

const cart: CartInterface = createCartObject();

const item: ItemInterface = {
	offerId: "1",
	name: "Nintendo Switch"
};

buyNow(cart, item);
```

![How software APIs are used.](What%20Is%20A%20Software%20API/Untitled.png)

How software APIs are used.

<aside>
<img src="https://app.notion.com/icons/info-alternate_blue.svg" alt="https://app.notion.com/icons/info-alternate_blue.svg" width="40px" /> Software APIs are more like contracts that need to be fulfilled.

</aside>