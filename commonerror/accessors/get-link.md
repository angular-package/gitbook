---
description: The get accessor gets the link(to read more about the thrown error)
---

# get link()

## `CommonError.prototype.link`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the link(to read more about the thrown error) by returning the [`#link`](../properties/link.md) property of a specified object.

{% code title="common-error.class.ts" %}
```typescript
public get link(): string | undefined {
  return this.#link;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)`|`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;">``</mark>

The **return type** is a [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type or [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined).

### Returns

The **return value** is the link of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

The **return value** is the error [identification](../../getting-started/basic-concepts.md#identification) of the generic type variable [`Id`](../generic-type-variables.md#wrap-opening) or [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

## Example usage

```typescript
// Example usage.
import { CommonError } from '@angular-package/error';

// Extend the `CommonError` class.
class TestError extends CommonError {}

// Returns "http://duckduckgo.com".
new TestError('problem', 'Fix accessor.', '(AE:427)', undefined, {
  link: 'http://duckduckgo.com',
}).link;
```
