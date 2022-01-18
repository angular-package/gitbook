# ⚠  textHasOpening()

{% hint style="danger" %}
The method does not yet exist.&#x20;
{% endhint %}

### `Wrapper.prototype.textHasOpening()`

Checks if the provided `text` has the opening of the specified [`Wrapper`](broken-reference) object at the beginning of the text.

{% code title="wrapper.class.ts" %}
```typescript
public textHasOpening(text: string): boolean {
  return (
    isStringType(text) && text.slice(0, this.opening.length) === this.opening
  );
}
```
{% endcode %}

#### Parameters

| Name: type     | Description                                                                                                                           |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `text: string` | The text of a `string` to test against the existence of the [`opening`](../../wrap/instance-accessors/#wrap.prototype.opening) chars. |

#### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the given `text` has the opening of the wrap.

#### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/text';

// Returns true of boolean.
new Wrapper(`[`, `]`).textHasOpening(`[quote]`);
```
