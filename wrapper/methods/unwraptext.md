# unwrapText()

## `Wrapper.prototype.unwrapText()`

The method returns the [primitive value](../../wrap/methods/valueof.md) of a specified [`Wrapper`](broken-reference) object with [`text`](../../wrap/accessors/get-text.md) unwrapped from the [`opening`](../../wrap/accessors/get-opening.md) and [`closing`](../../wrap/accessors/get-closing.md) chars of the [`Wrapper`](broken-reference) instance or given [`opening`](unwraptext.md#opening-string) and [`closing`](unwraptext.md#closing-string) chars.

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

Optional opening chars of [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type to remove from the **beginning** of the [`text`](../../wrap/accessors/get-text.md) of the [`Wrapper`](broken-reference) instance.

#### `closing: string`

Optional closing chars of [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type to remove from the **end** of the [`text`](../../wrap/accessors/get-text.md) of the [`Wrapper`](broken-reference) instance.

### Returns

The **return value** is the [primitive value](../../wrap/methods/valueof.md) of [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type with [`text`](../../wrap/accessors/get-text.md) unwrapped from the [`opening`](../../wrap/accessors/get-opening.md) and [`closing`](../../wrap/accessors/get-closing.md) chars of the [`Wrapper`](broken-reference) object or the given [`opening`](unwraptext.md#opening-string) and [`closing`](unwraptext.md#closing-string) chars.

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const longText = new Wrapper('{', '}', '{This is a long text}');

// Returns {This is a long text}.
longText.unwrapText();

// Returns {{This is a long text}}.
longText.unwrapText('', '');

// Returns {This is a long text}}.
longText.unwrapText('{', '');

// Returns {{This is a long text}.
longText.unwrapText('', '}');

// Returns {{This is a long text}}.
longText.unwrapText('{{', '}}');
```
