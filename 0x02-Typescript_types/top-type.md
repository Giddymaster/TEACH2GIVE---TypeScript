## Top Types
Top types in TypeScript are types that can represent any value without causing a type error.  
The two top types are:
- **`any`**: The most permissive type, allowing any value or operation.
- **`unknown`**: A safer alternative that enforces type checking before use.

### `any`  
The `any` type lets a variable hold any value, and TypeScript will not enforce type checking:

```typescript
let myVar: any = 55;
console.log(myVar); // 55

myVar = "Hello, World";
console.log(myVar); // Hello, World

myVar = [3, 12, 55];
console.log(myVar); // [3, 12, 55]

myVar = {};
console.log(myVar); // {}

console.log(myVar.toUpperCase()); // No error thrown
```
>Note: Avoid using any where possible, as it disables TypeScript’s type checking.

### `unknown`
The unknown type is similar to any but requires type checking before usage, making it a safer option.To use unknown safely, check the type before performing operations:

```ts
let myVar: unknown = "Hello";
// console.log(myVar.toUpperCase()); // Error

if (typeof myVar === "string") {// type checking 
  console.log(myVar.toUpperCase()); // Works fine
}
```