# ⚠  textHasClosing()

{% hint style="danger" %}
The method does not yet exist.
{% endhint %}

### `Wrapper.prototype.textHasClosing()`

Checks if the provided `text` has the closing of specified [`Wrapper`](../wrapper.md) object at the end of the text.

{% code title="wrapper.class.ts" %}
```typescript
public textHasClosing(text: string): boolean {
  return (
    isStringType(text) && text.slice(-this.closing.length) === this.closing
  );
}
```
{% endcode %}

#### Parameters

| Name: type     | Description                                                                                                                           |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `text: string` | The text of a `string` to test against the existence of the [`closing`](../../wrap/instance-accessors/#wrap.prototype.closing) chars. |

#### Returns

The return value is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the given `text` has the closing of the wrap.

#### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/text';

// Returns true of boolean.
new Wrapper(`[`, `]`).textHasClosing(`[quote]`);

// Returns false of boolean.
new Wrapper(`{{`, `}}`).textHasClosing(`{{variable`);
```



