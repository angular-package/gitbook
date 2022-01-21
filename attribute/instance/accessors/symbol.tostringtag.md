# \[Symbol.toStringTag]

### `[Symbol.toStringTag]`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor, with the help of [`toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag) of Symbol, changes the default object tag to `attribute` for an instance of the [`Attribute`](../../attribute.md).

{% hint style="info" %}
**Good to know:** The property can be read by the `typeOf()` function of the type package.
{% endhint %}

{% code title="attribute.class.ts" %}
```typescript
public get [Symbol.toStringTag](): string {
  return 'attribute';
}
```
{% endcode %}

### Example usage

```typescript
// Example usage.
import { Attribute } from '@angular-package/tag';
import { typeOf } from '@angular-package/type';

// Define the attribute.
const attributeColor = new Attribute('color', 'red');

// Returns 'attribute'.
typeOf(attributeColor);
```
