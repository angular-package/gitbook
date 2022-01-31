# \[Symbol.toStringTag]

## `[Symbol.toStringTag]`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor, with the help of [`toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag) of Symbol, changes the default object tag to `wrap` for an instance of the [`Wrap`](../../wrap.md).

{% hint style="info" %}
**Good to know:** The property can be read by the `typeOf()` function of the type package.
{% endhint %}

{% code title="wrap.class.ts" %}
```typescript
public get [Symbol.toStringTag](): string {
  return 'wrap';
}
```
{% endcode %}

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';
import { typeOf } from '@angular-package/type';

// Define the wrap.
const tagWrap = new Wrap('[', ']');

// Returns wrap.
typeOf(tagWrap);
```
