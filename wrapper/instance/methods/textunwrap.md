# textUnwrap()

## `Wrapper.prototype.textUnwrap()`

The method returns the [`text`](../../../wrap/accessors/instance/text.md) of the [`Wrapper`](broken-reference) object without its [`opening`](../../../wrap/accessors/instance/opening.md) and [`closing`](../../../wrap/accessors/instance/closing.md) chars or the given [`opening`](textunwrap.md#opening-string) and [`closing`](textunwrap.md#closing-string) chars.

{% hint style="info" %}
The default values for the `opening` and `closing` parameters are taken from the `Wrapper` object.
{% endhint %}

{% code title="wrapper.class.ts" %}
```typescript
public textUnwrap(
  opening: string = this.opening,
  closing: string = this.closing
): string {
  return Wrapper.unwrap(this.text, opening, closing);
}
```
{% endcode %}

### Parameters

#### `opening: string`

Optional **opening** chars of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type to remove from the **beginning** of the [`text`](../../../wrap/accessors/instance/text.md) of the [`Wrapper`](broken-reference) instance.

#### `closing: string`

Optional **closing** chars of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type to remove from the **end** of the [`text`](../../../wrap/accessors/instance/text.md) of the [`Wrapper`](broken-reference) instance.

### Returns

The **return value** is the [`text`](../../../wrap/accessors/instance/text.md) of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type without the [`opening`](../../../wrap/accessors/instance/opening.md) and [`closing`](../../../wrap/accessors/instance/closing.md) chars of the [`Wrapper`](broken-reference) object or given [`opening`](textunwrap.md#opening-string) and [`closing`](textunwrap.md#closing-string) chars.

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const longText = new Wrapper('{', '}', '{This is a long text}');

// Returns {{This is a long text}}.
longText.valueOf();

// Returns This is a long text.
longText.textUnwrap();

// Returns {This is a long text}.
longText.textUnwrap('', '');

// Returns This is a long text}.
longText.textUnwrap('{', '');

// Returns This is a long text.
longText.textUnwrap('{', undefined);

// Returns {This is a long text.
longText.textUnwrap('', '}');

// Returns This is a long text.
longText.textUnwrap(undefined, '}');
```
