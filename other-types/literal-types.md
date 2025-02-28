# Literal Types in TypeScript

Literal types allow variables to have specific values instead of general types like `string`, `number`, or `boolean`.

## 1. String Literal Types

A variable can only take predefined string values.

```typescript
type Status = "success" | "error" | "loading";

let state: Status = "success";
state = "loading";
state = "error";

// state = "failure"; // TypeScript error: Type '"failure"' is not assignable to type 'Status'
```

### 2. Template Literal Types

Template literal types allow the construction of new types using template literals, similar to JavaScript string templates.

```typescript
type Shade = "dark" | "light";
type Color = "red" | "green";

type ColorShade = `${Shade}-${Color}`;
// Equivalent to: "dark-red" | "dark-green" | "light-red" | "light-green"

let color: ColorShade = "light-green";
console.log(color); // Output: "light-green"

// color = "medium-red"; // TypeScript error: Type '"medium-red"' is not assignable to type 'ColorShade'
```

Literal types are powerful in defining strict and predictable types, reducing runtime errors while improving developer experience.
