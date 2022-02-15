---
description: Returns the `RangeError` instance of the given unique identification
---

# get()

## `RangeErrors.prototype.get()`

Returns the [`RangeError`](broken-reference) instance of the given [unique identification](../../getting-started/basic-concepts.md#unique-identification) [`id`](get.md#id-errorid) if set, otherwise [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

{% code title="range-errors.class.ts" %}
```typescript
public get<ErrorId extends Id>(id: ErrorId): RangeError<ErrorId> | undefined {
  return this.errors.get(id);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`ErrorId`</mark>`extends`[<mark style="color:green;">`Id`</mark>](../generic-type-variables.md#rangeerrors-less-than-id-greater-than)<mark style="color:green;">``</mark>

A generic type variable `ErrorId` constrained by the generic type variable [`Id`](../generic-type-variables.md#rangeerrors-less-than-id-greater-than) of the [`Errors`](broken-reference) object indicates the type picked from the [`Id`](../generic-type-variables.md#rangeerrors-less-than-id-greater-than) and its exact type is useful in picking the specific range error from the storage.

### Parameters

#### `id:`[<mark style="color:green;">`ErrorId`</mark>](get.md#erroridextendsid)<mark style="color:green;">``</mark>

The [unique identification](../../getting-started/basic-concepts.md#unique-identification) number of generic type variable [`ErrorId`](get.md#erroridextendsid) to pick an error from the object.

### Return type

#### `RangeError<`[<mark style="color:green;">`ErrorId`</mark>](get.md#erroridextendsid)`> |`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;">``</mark>

The **return type** is the [`RangeError`](broken-reference) object that takes the generic type variable [`ErrorId`](get.md#erroridextendsid) or [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined).

### Returns

The **return value** is the [`RangeError`](broken-reference) instance of the given [`id`](get.md#id-errorid) if set, otherwise [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

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

// Returns RangeError: ProblemRE: 4330: Age is 99 must be between 9 and 27 => Fix: Age must be
// of type RangeError<"EG: 4330", undefined, undefined> | undefined.
rangeErrors.get('RE: 4330');
```
