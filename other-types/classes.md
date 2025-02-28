# TypeScript Classes

TypeScript enhances OOP with features like access modifiers, abstract classes, and interfaces. Let's explore these concepts in-depth.

## 1. Understanding Access Modifiers

Access modifiers control property visibility within a class and its subclasses.

### a) private: Encapsulation

A private property or method is accessible only within the class. Encapsulation ensures that sensitive data is not directly modified from outside.

```typescript
class BankAccount {
  private balance: number;

  constructor(initialBalance: number) {
    this.balance = initialBalance;
  }

  deposit(amount: number): void {
    this.balance += amount;
    console.log(`Deposited ${amount}. New Balance: ${this.balance}`);
  }

  private calculateInterest(): number {
    return this.balance * 0.05;
  }
}

const myAccount = new BankAccount(1000);
myAccount.deposit(500);
// myAccount.balance; // Error: Property 'balance' is private
// myAccount.calculateInterest(); // Error: Method is private
```

### b) protected: Inheritance-Friendly

A protected property can be accessed within its class and subclasses. Use protected for properties that should be inherited but not exposed externally.

```typescript
class Employee {
  protected salary: number;

  constructor(salary: number) {
    this.salary = salary;
  }

  protected getSalary(): number {
    return this.salary;
  }
}

class Manager extends Employee {
  constructor(salary: number) {
    super(salary);
  }

  showSalary(): void {
    console.log(`Salary: ${this.getSalary()}`);
  }
}

const mgr = new Manager(5000);
mgr.showSalary();
// mgr.salary; // Error: Property 'salary' is protected
```

### c) public: Open Access

By default, all properties are public and can be accessed anywhere.Use public when there's no need to restrict access.

```typescript
class Car {
  public brand: string;

  constructor(brand: string) {
    this.brand = brand;
  }

  drive(): void {
    console.log(`Driving a ${this.brand}`);
  }
}

const myCar = new Car("Toyota");
console.log(myCar.brand); // Works
myCar.drive(); // Works
```

## 2. Abstract Classes

An abstract class defines a blueprint but cannot be instantiated. Use abstract when creating a base class with common behavior but requiring implementation of specific methods.

```typescript
abstract class Animal {
  constructor(public name: string) {}

  abstract makeSound(): void; // Must be implemented by subclasses

  move(): void {
    console.log(`${this.name} is moving`);
  }
}

class Cat extends Animal {
  makeSound(): void {
    console.log("Meow!");
  }
}

const kitty = new Cat("Whiskers");
kitty.makeSound(); // "Meow!"
kitty.move(); // "Whiskers is moving"
// const someAnimal = new Animal("Unknown"); // Error: Cannot create an instance of an abstract class
```

## 3. Classes Implementing Interfaces

An interface defines a contract that a class must follow. Interfaces enforce a structure but do not provide implementation.

```typescript
interface Vehicle {
  brand: string;
  speed: number;

  accelerate(amount: number): void;
}

class SportsCar implements Vehicle {
  brand: string;
  speed: number;

  constructor(brand: string, speed: number) {
    this.brand = brand;
    this.speed = speed;
  }

  accelerate(amount: number): void {
    this.speed += amount;
    console.log(`${this.brand} now going at ${this.speed} km/h`);
  }
}

const ferrari = new SportsCar("Ferrari", 100);
ferrari.accelerate(50); // "Ferrari now going at 150 km/h"
```

## 4. Combining Interfaces with Classes

A class can implement multiple interfaces.Use multiple interfaces to enforce multiple behaviors in a class.

```typescript
interface Flyer {
  fly(): void;
}

interface Swimmer {
  swim(): void;
}

class Duck implements Flyer, Swimmer {
  fly(): void {
    console.log("Duck is flying");
  }

  swim(): void {
    console.log("Duck is swimming");
  }
}

const donald = new Duck();
donald.fly(); // "Duck is flying"
donald.swim(); // "Duck is swimming"
```

## 5. Static Properties and Methods

static members belong to the class itself, not instances.Use static for constants or utility methods that don’t require an instance.

```typescript
class MathUtils {
  static PI = 3.14159;

  static circleArea(radius: number): number {
    return this.PI * radius * radius;
  }
}

console.log(MathUtils.PI); // 3.14159
console.log(MathUtils.circleArea(10)); // 314.159
```

## 6. Getters and Setters

Getters and setters provide controlled access to class properties.Use getters and setters to encapsulate validation logic.

```typescript
class Person {
  private _age: number;

  constructor(age: number) {
    this._age = age;
  }

  get age(): number {
    return this._age;
  }

  set age(newAge: number) {
    if (newAge < 0) {
      console.log("Age cannot be negative");
    } else {
      this._age = newAge;
    }
  }
}

const person = new Person(30);
console.log(person.age); // 30
person.age = -5; // "Age cannot be negative"
person.age = 35;
console.log(person.age); // 35
```

## Summary

`Access Modifiers`: private (encapsulation), protected (inheritance), public (default).
`Abstract Classes`: Define blueprints, cannot be instantiated, enforce method implementation.
`Interfaces`: Define structure without implementation, support multiple interfaces in a class.
`Static Members`: Class-level properties and methods.
`Getters and Setters`: Provide controlled access to properties.
