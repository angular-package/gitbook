# toWrap()

## `Wrapper.prototype.toWrap()`

Returns the [`Wrap`](broken-reference) instance consists of the [`text`](../../wrap/accessors/get-text.md), [`opening`](../../wrap/accessors/get-opening.md) and [`closing`](../../wrap/accessors/get-closing.md) chars of the [`Wrapper`](broken-reference) object.

{% code title="wrapper.class.ts" %}
```typescript
public toWrap(): Wrap<Opening, Text, Closing> {
  return new Wrap(this.opening, this.closing, this.text);
}
```
{% endcode %}

### Return type

#### `Wrap<`<mark style="color:green;">`Opening`</mark>`,`<mark style="color:green;">`Text`</mark>`,`<mark style="color:green;">`Closing`</mark>`>`

The **return type** is the [`Wrap`](broken-reference) object that takes generic type variables [`Opening`](../generic-type-variables.md#wrap-opening), [`Text`](../generic-type-variables.md#wrapper-less-than...-text-...greater-than) and [`Closing`](../generic-type-variables.md#wrap-closing).

### Returns

The **return value** is an instance of [`Wrap`](broken-reference) consisting of the [`text`](../../wrap/accessors/get-text.md), [`opening`](../../wrap/accessors/get-opening.md), and [`closing`](../../wrap/accessors/get-closing.md) chars of the [`Wrapper`](broken-reference) object.

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const longText = new Wrapper('{', '}', '{This is a long text}');

// Returns Wrap {'{{This is a long text}}'}.
longText.toWrap();
```
