# Type Inference in TypeScript

Type inference allows TypeScript to automatically determine a variable’s type based on its assigned value, eliminating the need for explicit type annotations.

## Example  

```typescript
let message = "Hello, TypeScript"; // Inferred as string
let count = 10; // Inferred as number
```

Since `message` is initialized with a string and `count` with a number, TypeScript assigns them the respective types, preventing incorrect reassignments.

```ts
let message = "Hello, TypeScript"; // Inferred as string
let count = 10; // Inferred as number

message = 200; // Error: Type 'number' is not assignable to type 'string'
count = "Hello, world"; // Error: Type 'string' is not assignable to type 'number'
```
