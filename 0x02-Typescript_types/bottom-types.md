# Bottom Types

In TypeScript, a bottom type is a type that represents a value that never exists.

The only bottom type in TypeScript is `never`, which is a type that represents values that never occur.

The `never` type is used in situations where a value can never be observed.

This usually happens in:

- Functions that never return (e.g., infinite loops and errors)
- Exhaustive switch-case handling
- Unreachable code

## Example

```typescript
function throwError(message: string): never {
    throw new Error(message);
}

function infiniteLoop(): never {
    while (true) {
        console.log("This will run forever");
    }
}
```
    
    This example demonstrates how `never` is used in functions that either throw an error or run indefinitely.
