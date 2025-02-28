# Type Guards and Narrowing in TypeScript

Type guards are essential for ensuring safe type handling in TypeScript. Let's explore more advanced use cases of instanceof, typeof, and type predicates.

## 1. instanceof with Class Inheritance

The instanceof operator works well with class hierarchies.

```typescript
class Animal {
  makeSound() {
    console.log("Animal making sound");
  }
}

class Dog extends Animal {
  bark() {
    console.log("Woof! Woof!");
  }
}

const pet: Animal = new Dog();

if (pet instanceof Dog) {
  pet.bark(); // Works because TypeScript now knows it's a Dog
} else {
  pet.makeSound();
}
```

## 2. typeof for Multiple Primitive Types

The typeof operator is useful when handling multiple primitive types.

```typescript
function processValue(value: string | number | boolean): void {
  if (typeof value === "string") {
    console.log(value.toUpperCase());
  } else if (typeof value === "number") {
    console.log(value * 10);
  } else {
    console.log(value ? "It's true!" : "It's false!");
  }
}

processValue(5); // 50
processValue("hello"); // HELLO
processValue(false); // It's false!
```

## 3. Custom Type Predicate (is Operator)

Using type predicates makes custom type checks more readable.

```typescript
type Car = { drive: () => void };
type Boat = { sail: () => void };

function isCar(vehicle: Car | Boat): vehicle is Car {
  return (vehicle as Car).drive !== undefined;
}

function operateVehicle(vehicle: Car | Boat) {
  if (isCar(vehicle)) {
    vehicle.drive();
  } else {
    vehicle.sail();
  }
}

const myCar: Car = { drive: () => console.log("Driving...") };
const myBoat: Boat = { sail: () => console.log("Sailing...") };

operateVehicle(myCar); // "Driving..."
operateVehicle(myBoat); // "Sailing..."
```

## 4. Type Guards with in Operator

The in operator is useful when checking for object properties dynamically.

```typescript
type Programmer = { code: () => void };
type Designer = { design: () => void };

function isProgrammer(person: Programmer | Designer): person is Programmer {
  return "code" in person;
}

function work(person: Programmer | Designer) {
  if (isProgrammer(person)) {
    person.code();
  } else {
    person.design();
  }
}

const dev: Programmer = { code: () => console.log("Writing code...") };
const artist: Designer = { design: () => console.log("Creating designs...") };

work(dev); // "Writing code..."
work(artist); // "Creating designs..."
```

## 5. Combining Multiple Type Guards

You can combine multiple type guards for more flexible checks.

```typescript
function describeInput(input: string | number | boolean | null): string {
  if (input === null) {
    return "Input is null";
  } else if (typeof input === "string") {
    return `String input: ${input}`;
  } else if (typeof input === "number") {
    return `Number input: ${input * 2}`;
  } else {
    return `Boolean input: ${input ? "True" : "False"}`;
  }
}

console.log(describeInput("TypeScript")); // "String input: TypeScript"
console.log(describeInput(42)); // "Number input: 84"
console.log(describeInput(true)); // "Boolean input: True"
console.log(describeInput(null)); // "Input is null"
```

## Summary

`instanceof` → Works well with classes and inheritance.
`typeof `→ Best for checking primitive types (string, number, boolean).
`is Type Predicate` → Useful for distinguishing between custom types.
`in Operator` → Checks for property existence in objects.
`Combining Type Guards` → Helps when working with multiple complex types.
