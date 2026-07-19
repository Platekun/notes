---
Note Type: "Literature"
Author: "Robert Martin"
Primary Zettelkasten Area: "Object Oriented Programming"
Last edited time: "September 20, 2023 2:23 AM"
Status: "Processed"
Created time: "October 18, 2022 12:58 AM"
Sources: "Data Structure And Objects"
---

# Data Structures VS Objects

This difference between objects and data structures come from the C++ era where the difference was more notorious. It’s harder to explain in modern languages which implement Java-like object oriented programming.

Data structures refer to things **that hold no behavior and only expose *data* as a public container , just like database tables displaying no hint behavior:

```tsx
interface IVehicleDataStructure {
	engine: IEngine;
	wheels: Array<IWheel>;
}
```

On the other side there is *behavior*, what we can do with a certain thing without having to know its details:

```tsx
interface IVehicleBehavior {
	startEngine(): void;
  shiftInto(gear: number): void;
  accelerate(amount: number): void;
  brake(amount: number): void;
}
```

`IVehicle` could be any kind of vehicle without limitations because the details of the are not exposed to the world. Implementors of this interface will find that Its *data* can be changed easily because nobody else knows about its internals. The opposite is also true as well, its behavior is now hard to change because everybody knows about it.

If we followed the rules of modern object oriented programming, we would attempt to write a thing that hides data and expose behavior. Inputs could be transformed into outputs but we do not know where or how data is stored.

```tsx
class Vehicle {
	private engine: Engine;
	private wheels: Array<IWheel>;
	public startEngine() {}
  public shiftInto(gear: number) {}
  public accelerate(amount: number) {}
  public brake(amount: number) {}
}
```

> *Are objects more about behavior or data?  From the outside looking in the data are hidden and the behaviors are exposed. We see inputs transformed into outputs; but see none of the data sequestered within; nor do we know where or how that data are stored.

Are database tables more about behavior or data?  They are simple data structures. From the outside looking in the data are exposed and no behavior is visible or even implied.*
> 

[https://twitter.com/unclebobmartin/status/1231216430839992320](https://twitter.com/unclebobmartin/status/1231216430839992320)

[https://twitter.com/unclebobmartin/status/1231216431892770816](https://twitter.com/unclebobmartin/status/1231216431892770816)