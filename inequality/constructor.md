---
description: The `Inequality` primitive wrapper object constructor
---

# Constructor

## `Inequality()`

Creates a child class instance with the given primitive [`value`](constructor.md#value-value).

```typescript
constructor(value: Value) {
  super(value);
  this.#greater = new Greater(value);
  this.#less = new Less(value);
}
```

### Parameters

#### `value:`<mark style="color:green;">`Value`</mark>

The value of the generic type variable [`Value`](generic-type-variables.md#inequality-less-than-value-greater-than) is the [primitive value](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) of a new child class instance.

## Example usage

```typescript
// Example usage.
import { Inequality } from '@angular-package/range';

// Define the `Age` class and extend it with `Inequality`.
class Age<Value extends number> extends Inequality<Value> {}

// Initialize `Age`.
const age = new Age(27);

// Returns Age {27} of Age<27>.
age;
```
