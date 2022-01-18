# isOpeningIn()

### `Wrapper.prototype.isOpeningIn()`

Checks whether the provided `text` has the [`opening`](../../wrap/instance-accessors/#wrap.prototype.opening) chars of a specified [`Wrapper`](../wrapper.md) object at the **beginning**.

{% code title="wrapper.class.ts" %}
```typescript
public isOpeningIn(text: string): boolean {
  return Wrapper.hasOpening(text, this.opening);
}
```
{% endcode %}

### Parameters

| Name: type     | Description                                                                                                                                                                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `text: string` | The **text** of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) to test for the existence of the [`opening`](../../wrap/instance-accessors/#wrap.prototype.opening) chars at the **beginning** of it. |

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the given `text` has the [`opening`](../../wrap/instance-accessors/#wrap.prototype.opening) chars  of the wrap.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
