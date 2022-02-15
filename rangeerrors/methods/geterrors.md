---
description: Returns the object of set errors
---

# getErrors()

## `RangeErrors.prototype.getErrors()`

Returns an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of set range errors, where the key is a [unique identification](../../getting-started/basic-concepts.md#unique-identification).

{% code title="range-errors.class.ts" %}
```typescript
public getErrors(): { [Key in Id]: RangeError<Key> | undefined } {
  return Object.fromEntries(this.errors.entries()) as any;
}
```
{% endcode %}

### Return type

#### `{ [`<mark style="color:green;">`Key`</mark>`in`[<mark style="color:green;">`Id`</mark>](../generic-type-variables.md#rangeerrors-less-than-id-greater-than)`]: RangeError<`<mark style="color:green;">`Key`</mark>`> |`<mark style="color:green;">`undefined`</mark>` ``}`

The **return type** is an object of the  [`RangeError`](broken-reference) objects or [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) in the keys of generic type variable [`Id`](../generic-type-variables.md#rangeerrors-less-than-id-greater-than).

### Returns

The **return value** is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of set errors.

## Example usage

```typescript
// Example usage.
import { RangeErrors } from '@angular-package/error';

// Define range errors.
const rangeErrors = new RangeErrors('RE: 4332', 'RE: 4331', 'RE: 4330');

// Set the `RangeError` objects under the given identification numbers.
rangeErrors
  .set(
    'Age is 99',
    'Age must be',
    'RE: 4330',
    9,
    27
  )
  .set('Detected numbers', 'Provide only letters', 'RE: 4331');

/*
Returns
{
  RE: 4330: ...,
  RE: 4331: ...
}
of type
  {
    "RE: 4332": RangeError<"RE: 4332", undefined, undefined> | undefined;
    "RE: 4331": RangeError<"RE: 4331", undefined, undefined> | undefined;
    "RE: 4330": RangeError<"RE: 4330", undefined, undefined> | undefined;
  }
*/
rangeErrors.getErrors();
```
