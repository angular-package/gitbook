# unwrapText()

## `Wrapper.prototype.unwrapText()`

The method returns the primitive value of a specified [`Wrapper`](broken-reference) object with text unwrapped from its [`opening`](../../wrap/accessors/#wrap.prototype.opening) and [`closing`](../../wrap/accessors/#wrap.prototype.closing) chars or given [`opening`](unwraptext.md#opening-string) and [`closing`](unwraptext.md#closing-string) chars.

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

#### `opening: string`

Optional opening chars of [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type to remove from the **beginning** of the [`text`](../../wrap/accessors/#wrap.prototype.text) of the [`Wrapper`](../description.md) instance.

#### `closing: string`

Optional closing chars of [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type to remove from the **end** of the [`text`](../../wrap/accessors/#wrap.prototype.text) of the [`Wrapper`](../description.md) instance.

### Returns

The **return value** is the primitive value of [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type with [`text`](../../wrap/accessors/#wrap.prototype.text) unwrapped from the [`opening`](../../wrap/accessors/#wrap.prototype.opening) and [`closing`](../../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](broken-reference) object or the given [`opening`](unwraptext.md#opening-string) and [`closing`](unwraptext.md#closing-string) chars.

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
