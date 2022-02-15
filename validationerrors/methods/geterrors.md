---
description: Returns the object of set validation errors
---

# getErrors()

## `ValidationErrors.prototype.getErrors()`

Returns the object of set validation errors, where the key is a [unique identification](../../getting-started/basic-concepts.md#unique-identification).

{% code title="validation-errors.class.ts" %}
```typescript
public getErrors(): { [Key in Id]: ValidationError<Key> | undefined } {
  return Object.fromEntries(this.errors.entries()) as any;
}
```
{% endcode %}

### Return type

#### `{ [`<mark style="color:green;">`Key`</mark>`in`[<mark style="color:green;">`Id`</mark>](../generic-type-variables.md#validationerrors-less-than-id-greater-than)`]:`[<mark style="color:green;">`ValidationError`</mark>](broken-reference)`<`[<mark style="color:green;">`Id`</mark>](../generic-type-variables.md#validationerrors-less-than-id-greater-than)`> }`

The **return type** is an object of the [`ValidationError`](broken-reference) objects in the keys of generic type variable [`Id`](../generic-type-variables.md#validationerrors-less-than-id-greater-than).

### Returns

The **return value** is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of set errors.

## Example usage

```typescript
// Example usage.
import { ValidationErrors } from '@angular-package/error';

// Define validation errors.
const validationErrors = new ValidationErrors(
  '(VE: 4332)',
  '(VE: 4331)',
  '(VE: 4330)'
);

// Set the `ValidationError` objects under the given identification numbers.
validationErrors
  .set('Age is 99', 'Age must be', '(VE: 4330)')
  .set('Detected numbers', 'Provide only letters', '(VE: 4331)');

/*
  Returns:
  {
    (VE: 4330): ...,
    (VE: 4331): ...
  }
  of type
  {
    "(VE: 4332)": ValidationError<"(VE: 4332)"> | undefined;
    "(VE: 4331)": ValidationError<"(VE: 4331)"> | undefined;
    "(VE: 4330)": ValidationError<"(VE: 4330)"> | undefined;
  }
*/
validationErrors.getErrors();
```
