---
description: Returns the object of set type errors
---

# getErrors()

## `TypeErrors.prototype.getErrors()`

Returns the [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of set type errors, where the key is a [unique identification](../../getting-started/basic-concepts.md#unique-identification).

{% code title="type-errors.class.ts" %}
```typescript
public getErrors(): { [Key in Id]: TypeError<Key, string> } {
  return Object.fromEntries(this.errors.entries()) as any;
}
```
{% endcode %}

### Return type

#### `{ [`<mark style="color:green;">`Key`</mark>`in`[<mark style="color:green;">`Id`</mark>](../generic-type-variables.md#typeerrors-less-than-id-greater-than)`]: TypeError<`<mark style="color:green;">`Key`</mark>`> |`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) `}`

The **return type** is an object of the [`TypeError`](broken-reference) objects or [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) in the keys of generic type variable [`Id`](../generic-type-variables.md#typeerrors-less-than-id-greater-than).

### Returns

The **return value** is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of set errors.

## Example usage

```typescript
// Example usage.
import { TypeErrors } from '@angular-package/error';

// Define type errors.
const typeErrors = new TypeErrors('(TE: 4332)', '(TE: 4331)', '(TE: 4330)');

// Set the `TypeError` objects under the given identification numbers.
typeErrors
  .set(
    'Age is 99',
    'Age must be',
    '(TE: 4330)',
    'string',
  )
  .set('Detected numbers', 'Provide only letters', '(TE: 4331)', 'number');

/*
  Returns {
    (TE: 4330): ...,
    (TE: 4331): ...
  }
  of type
  {
    "(TE: 4332)": TypeError<"(TE: 4332)", undefined> | undefined;
    "(TE: 4331)": TypeError<"(TE: 4331)", undefined> | undefined;
    "(TE: 4330)": TypeError<"(TE: 4330)", undefined> | undefined;
  }
*/
typeErrors.getErrors();
```
