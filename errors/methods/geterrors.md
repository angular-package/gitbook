---
description: The method returns the object of set errors
---

# getErrors()

## `Errors.prototype.getErrors()`

Returns an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of set errors, where the key is a [unique identification](../../getting-started/basic-concepts.md#unique-identification).

{% code title="errors.class.ts" %}
```typescript
public getErrors(): { [Key in Id]: Error<Key> | undefined } {
  return Object.fromEntries(this.errors.entries()) as any;
}
```
{% endcode %}

### Return type

#### `{ [`<mark style="color:green;">`Key`</mark>`in`[<mark style="color:green;">`Id`</mark>](../generic-type-variables.md#errors-less-than-id-greater-than)`]: Error<`<mark style="color:green;">`Key`</mark>`> |`<mark style="color:green;">`undefined`</mark>` ``}`

A **return type** is an object of the [`Error`](broken-reference) objects or [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) in the keys of generic type variable [`Id`](../generic-type-variables.md#errors-less-than-id-greater-than).

### Returns

The **return value** is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of set errors.

## Example usage

```typescript
// Example usage.
import { Errors } from '@angular-package/error';

// Define general errors.
const generalErrors = new Errors('EG: 4332', 'EG: 4331', 'EG: 4330');

// Set the `Error` objects under the given identification numbers.
generalErrors
  .set(
    'Bad parameter type, detected number',
    'Provide proper type, the `string`',
    'EG: 4330'
  )
  .set('Detected numbers', 'Provide only letters', 'EG: 4331');

// Returns:
/*
Returns
  {
    EG: 4330: ...,
    EG: 4331: ...
  }
  of type
  {
    "EG: 4332": Error<"EG: 4332">;
    "EG: 4331": Error<"EG: 4331">;
    "EG: 4330": Error<"EG: 4330">;
  }
*/
generalErrors.getErrors();
```
