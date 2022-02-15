---
description: Returns the `TypeError` instance of the given unique identification
---

# get()

## `TypeErrors.prototype.get()`

Returns the [`TypeError`](broken-reference) instance of the given [unique identification](../../getting-started/basic-concepts.md#unique-identification) [`id`](get.md#id-errorid) if set, otherwise [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

{% code title="type-errors.class.ts" %}
```typescript
public get<ErrorId extends Id>(id: ErrorId): TypeError<ErrorId> | undefined {
  return this.errors.get(id);
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`ErrorId`</mark>`extends`[<mark style="color:green;">`Id`</mark>](../../rangeerrors/generic-type-variables.md#rangeerrors-less-than-id-greater-than)<mark style="color:green;">``</mark>

A generic type variable `ErrorId` constrained by the generic type variable [`Id`](../../rangeerrors/generic-type-variables.md#rangeerrors-less-than-id-greater-than) of the [`Errors`](broken-reference) object indicates the type picked from the [`Id`](../../rangeerrors/generic-type-variables.md#rangeerrors-less-than-id-greater-than) and its exact type is useful in picking the specific range error from the storage.

### Parameters

#### `id:`[<mark style="color:green;">`ErrorId`</mark>](get.md#erroridextendsid)<mark style="color:green;">``</mark>

The [unique identification](../../getting-started/basic-concepts.md#unique-identification) number of generic type variable [`ErrorId`](get.md#erroridextendsid) to pick an error from the object.

### Return type

#### `TypeError<`[<mark style="color:green;">`ErrorId`</mark>](get.md#erroridextendsid)`> |`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;">``</mark>

The **return type** is the [`TypeError`](broken-reference) object that takes the generic type variable [`ErrorId`](get.md#erroridextendsid) or [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined).

### Returns

The **return value** is the [`TypeError`](broken-reference) instance of the given [`id`](get.md#id-errorid) if set, otherwise [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

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
  Returns TypeError: Problem(TE: 4330): Age is 99 => Fix: Age must be must be of the string
  of type
  TypeError<"(TE: 4330)", undefined> | undefined
*/
typeErrors.get('(TE: 4330)');

// Returns undefined of type TypeError<"(TE: 4332)", undefined> | undefined
typeErrors.get('(TE: 4332)');
```
