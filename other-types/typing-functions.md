# Callback with an Optional Parameter

A callback function can have an optional parameter, allowing it to be invoked with or without that argument.

```typescript
function greet(name: string, callback?: (message: string) => void): void {
  console.log(`Hello, ${name}`);
  if (callback) {
    callback(`You are a great person, ${name}`);
  }
}

greet("Gideon mwangi", (message) => console.log(message)); // With callback
greet("Jane mwangi"); // Without callback
```

## Callback with a Default Parameter

A callback function can also have a default parameter.

```typescript
function greet(
  name: string,
  callback: (message: string) => void = (msg) => console.log(msg)
): void {
  console.log(`Hello, ${name}`);
  callback(`You are a great person, ${name}`);
}

greet("Gideon mwangi", (message) => console.log(`Custom Message: ${message}`)); // Using a custom callback
greet("Jane mwangi"); // Using the default callback
```

## Callback with Both Optional and Default Parameters

We can combine both optional and default parameters in a callback.

```typescript
function greet(
  name: string,
  callback?: (message: string) => void
): void {
  console.log(`Hello, ${name}`);
  if (callback) {
    callback(`You are a great person, ${name}`, "Have a great day!");
  }
}

greet("Gideon"); // No callback
greet("Gideon", (message = "You're great!") => console.log(message)); // Callback with default parameter
greet("Gideon", (message) => console.log(message)); // Callback with provided parameter
```
