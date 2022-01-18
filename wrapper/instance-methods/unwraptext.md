# unwrapText()

### `Wrapper.prototype.unwrapText()`

The method returns the primitive value of a specified `Wrapper` object with text unwrapped from its [`opening`](../../wrap/instance-accessors/#wrap.prototype.opening) and [`closing`](../../wrap/instance-accessors/#wrap.prototype.closing) chars or given `opening` and `closing` chars.

{% code title="wrapper.class.ts" %}
```typescript
public unwrapText(
  opening: string = this.opening,
  closing: string = this.closing
): string {
  return `${this.opening}${Wrapper.unwrap(this.text, opening, closing)}${
    this.closing
  }`;
} 
```
{% endcode %}

### Parameters

| Name: type        | Description                                                                                                                                                                                                                                                      |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `opening: string` | Optional opening chars of [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type to remove from the **beginning** of the [`text`](../../wrap/instance-accessors/#wrap.prototype.text) of the [`Wrapper`](../wrapper.md) instance. |
| `closing: string` | Optional closing chars of [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type to remove from the **end** of the [`text`](../../wrap/instance-accessors/#wrap.prototype.text) of the [`Wrapper`](../wrapper.md) instance.       |

### Returns

The **return value** is the primitive value of [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type with [`text`](../../wrap/instance-accessors/#wrap.prototype.text) unwrapped from the [`opening`](../../wrap/instance-accessors/#wrap.prototype.opening) and [`closing`](../../wrap/instance-accessors/#wrap.prototype.closing) chars of the `Wrapper` object or the given `opening` and `closing` chars.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
