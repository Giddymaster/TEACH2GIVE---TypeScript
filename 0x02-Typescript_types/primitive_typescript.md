## Primitive Types
Primitive types in TypeScript are the fundamental data types representing simple, immutable values. These include `boolean`, `number`, `string`, `undefined`, and `null`.

### Numbers  
Numeric values can be positive, negative, zero, +Infinity, -Infinity, or floating-point numbers.  
Use the `number` keyword to define number data types:

```typescript
const myInteger: number = 15;
const negative: number = -35;
const myFloat: number = 234.67;
const zero: number = 0;
const infinity: number = Infinity;
const negativeInfinity: number = -Infinity;
```

### Strings
A string is a sequence of characters enclosed in double ("), single ('), or backticks (`).
Use the string keyword to define string data types:

```typescript
const firstName: string = "Gideon";
const lastName: string = "Mwangi";
const emailAddress: string = `mwangig6@gmail.com`;
const fullName: string = `${firstName} ${lastName}`;
```

### Booleans
Booleans represent true or false values.
Use the boolean keyword to define a boolean data type:

```typescript
const isMale: boolean = true;
const isFemale: boolean = false;
```

### null
null explicitly defines something as empty or non-existent.
By default, null variables can hold any data type:

```typescript
let result = null;
result = true;
result = "John";
result = 25;
```
To restrict a variable to null only:
```typescript
let result: null = null;
```

### undefined
undefined represents a declared variable that has not yet been assigned a value.
It has its own keyword: `undefined.`