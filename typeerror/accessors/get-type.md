---
description: The `get` accessor obtains the type
---

# get type()

## ​`TypeError.prototype.type`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor obtains the type of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) that causes an error to be thrown(or not thrown) if set, otherwise returns [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

{% code title="type-error.class.ts" %}
```typescript
public get type(): string | undefined {
  return this.#type;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;"></mark>[<mark style="color:green;">string</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) | [<mark style="color:green;">undefined</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;"></mark>

### Returns

The **return value** is the type of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

## Example usage

```typescript
// Example usage.
import { TypeError } from '@angular-package/error';

// Returns "string".
new TypeError('problem', 'Fix accessor.', '(TE:201)', 'string').type;
```
