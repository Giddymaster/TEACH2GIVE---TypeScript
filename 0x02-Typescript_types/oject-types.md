# Object Types in TypeScript

Object types define the structure of complex values in TypeScript.  

## Common Object Types

- **Interface** – Specifies an object’s structure.  
- **Class** – Acts as a blueprint for objects.  
- **Enum** – Defines a set of named constants.  
- **Array** – Represents a collection of values of the same type.  
- **Tuple** – Stores an ordered set of elements with specific types and lengths.  

## Interfaces

Interfaces help enforce structure and type safety in objects.

```typescript
interface Person {
  name: string;
  age: number;
  isStudent?: boolean; // Optional property due to ?
}

const Gideon: Person = {
  name: "Gideon",
  age: 22
};

console.log(Gideon);
```

### Readonly Properties

The readonly keyword prevents modifications to specific properties.

```typescript
interface Employee {
  readonly id: number;
  name: string;
}

const emp: Employee = { id: 101, name: "Gideon" };
// emp.id = 102; // Error: Cannot modify a readonly property
```

### Extending Interfaces

An interface can inherit properties from another interface.

```typescript
interface BaseUser {
  username: string;
  email: string;
}

interface Admin extends BaseUser {
  accessLevel: string;
}

const adminUser: Admin = {
  username: "admin123",
  email: "admin@example.com",
  accessLevel: "super"
};
```

### Classes

A class defines a template for creating objects.

```typescript
class Car {
  brand: string;
  model: string;

  constructor(brand: string, model: string) {
    this.brand = brand;
    this.model = model;
  }

  displayInfo() {
    console.log(`Car: ${this.brand} ${this.model}`);
  }
}

const myCar = new Car("Toyota", "Corolla");
myCar.displayInfo();
```

### Enums

Enums define a fixed set of named values.

### Numeric Enums

```typescript
enum Direction {
  Up,    // 0
  Down,  // 1
  Left,  // 2
  Right  // 3
}

console.log(Direction.Left); // Output: 2
```

### String Enums

```typescript
enum AccessLevel {
  User = "USER",
  Admin = "ADMIN",
  SuperAdmin = "SUPER_ADMIN"
}

console.log(AccessLevel.Admin); // Output: ADMIN
```

### Arrays

An array holds multiple values of the same type.

```typescript
let scores: number[] = [90, 85, 78];
console.log(scores);
```

To store mixed types:

```typescript
let mixedData: (string | number)[] = ["Gideon", 25, "Bob", 30];
console.log(mixedData);
```

### Tuples

Tuples store elements with fixed types and positions.

```typescript
let userInfo: [string, number] = ["Gideon", 25];
console.log(userInfo);
```

### Named Tuples

```typescript
let border: [width: string, style: string, color?: string] = ["2px", "solid", "blue"];
console.log(border);
Tuples provide better structure for ordered data while ensuring type safety.
```
