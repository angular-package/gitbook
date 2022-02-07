# toArray()

## `Wrapper.prototype.toArray()`

Returns an [`array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) consisting of the [`opening`](../../wrap/accessors/get-opening.md) chars, [`text`](../../wrap/accessors/get-text.md), and [`closing`](../../wrap/accessors/get-closing.md) chars.

{% code title="wrapper.class.ts" %}
```typescript
public toArray(): readonly [Opening, Text, Closing] {
  return [this.opening, this.text, this.closing];
}
```
{% endcode %}

### Return type

#### `readonly [`<mark style="color:green;">`Opening`</mark>`,`<mark style="color:green;">`Text`</mark>`,`<mark style="color:green;">`Closing`</mark>`]`

The **return type** is a **read-only** [`array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of generic type variables in order [`Opening`](../generic-type-variables.md#wrap-opening), [`Text`](../generic-type-variables.md#wrapper-less-than...-text-...greater-than) and [`Closing`](../generic-type-variables.md#wrap-closing).

### Returns

The **return value** is a **read-only** [`array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) consisting of the [`opening`](../../wrap/accessors/get-opening.md) chars, [`text`](../../wrap/accessors/get-text.md), and [`closing`](../../wrap/accessors/get-closing.md) chars.

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const longText = new Wrapper('{', '}', '{This is a long text}');

// Returns ['{', '{This is a long text}', '}'].
longText.toArray();
```
