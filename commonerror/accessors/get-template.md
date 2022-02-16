---
description: The get accessor gets the template of the error message
---

# get template()

## `CommonError.prototype.template`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the [template](../../getting-started/basic-concepts.md#template) of the error message by returning the [`#template`](../properties/template.md) property of a specified object.

{% code title="common-error.class.ts" %}
```typescript
public get template(): string {
  return this.#template;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)<mark style="color:green;">``</mark>

### Returns

The **return value** is the [template](../../getting-started/basic-concepts.md#template) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

## Example usage

```typescript
// Example usage.
import { CommonError } from '@angular-package/error';

// Extend the `CommonError` class.
class TestError<Id extends string> extends CommonError<Id> {}

// Returns "{problem} {fix} {id}".
new TestError(
  'Problem accessor.',
  'Fix accessor.',
  '(AE:427)',
  '{problem} {fix} {id}'
).template;
```
