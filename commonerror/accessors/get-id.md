---
description: The get accessor gets the error identification
---

# get id()

## `CommonError.prototype.id`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the error [identification](../../getting-started/basic-concepts.md#identification) by returning the [`#id`](../properties/id.md) property of a specified object.

{% code title="common-error.class.ts" %}
```typescript
public get id(): Id | undefined {
  return this.#id;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`Id`</mark>](../generic-type-variables.md#commonerror-less-than-id-greater-than)`|`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;">``</mark>

The **return type** is the generic type variable [`Id`](../generic-type-variables.md#commonerror-less-than-id-greater-than) or [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined).

### Returns

The **return value** is the error [identification](../../getting-started/basic-concepts.md#identification) of the generic type variable [`Id`](../generic-type-variables.md#commonerror-less-than-id-greater-than) or [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

## Example usage

```typescript
// Example usage.
import { CommonError } from '@angular-package/error';

// Extend the `CommonError` class.
class TestError<Id extends string> extends CommonError<Id> {}

// Returns "(AE:427)".
new TestError('problem', 'Fix accessor.', '(AE:427)').id;
```
