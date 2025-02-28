# Combining Types in TypeScript

TypeScript provides multiple ways to combine and manipulate types for better flexibility and code reuse.
Some key techniques include:

## 1. Union Types (`|`)

Union types allow a variable to hold values of different types.

```typescript
let myVariable: string | number;

myVariable = "Hello, World!"; // Valid
myVariable = 44; // Valid
myVariable = false; // Invalid (TypeScript error)
```

### 2. Type Aliases (type)

Type aliases provide custom names for complex types, making them easier to read and reuse.

```typescript
type IDNumber = string | number;

let userId: IDNumber = 35552;
let anotherId: IDNumber = "LkVH281";

console.log(userId, anotherId);
```

Aliases can also be used with objects:

```typescript
type User = {
  firstName: string;
  lastName: string;
  age: number;
};

const Gideon: User = {
  firstName: "Gideon",
  lastName: "mwangi",
  age: 34,
};

console.log(Gideon);
```

### 3. Intersection Types (&)

Intersection types allow you to merge multiple types into one. The resulting type must satisfy all combined types.

```typescript
interface Person {
  firstName: string;
  lastName: string;
}

interface PersonDetails {
  location: string;
  email: string;
  phoneNumber: string;
}

type Employee = Person & PersonDetails;

const Gideon: Employee = {
  firstName: "Gideon",
  lastName: "mwangi",
  location: "Murang'a ST",
  email: "Gideon@gmail.com",
  phoneNumber: "+234023849453",
};

console.log(Gideon);
```

### 4. keyof Operator

The keyof operator extracts the keys of an object type as a union of string or numeric literal types.

```typescript
interface Person {
  firstName: string;
  lastName: string;
  age: number;
}

type Keys = keyof Person;

let x: Keys = "firstName";
let y: Keys = "lastName";
let z: Keys = "age";

console.log(x, y, z);

// Type '"Hello, World"' is not assignable to type 'keyof Person'
let something: Keys = "Hello, World"; // TypeScript error
```
