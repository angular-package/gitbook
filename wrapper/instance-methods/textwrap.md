# textWrap()

### `Wrapper.prototype.textWrap()`

The method returns the [`text`](../../wrap/instance/accessors/#wrap.prototype.text) of the [`Wrapper`](../wrapper.md) object wrapped by the given [`opening`](../../wrap/instance/accessors/#wrap.prototype.opening) and [`closing`](../../wrap/instance/accessors/#wrap.prototype.closing) chars.

{% code title="wrapper.class.ts" %}
```typescript
public textWrap<TextOpening extends string, TextClosing extends string>(
  opening: TextOpening,
  closing: TextClosing
): Wrapped<TextOpening, Text, TextClosing> {
  return new Wrap(opening, closing, this.text).valueOf();
}
```
{% endcode %}

| Generic type variables                                                                                                                                                                                                                                                                                                                                                                          | Name |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---- |
| <p><strong><code>TextOpening extends string</code></strong></p><p>A generic type variable constrained by the <a href="https://www.typescriptlang.org/docs/handbook/basic-types.html#string"><code>string</code></a>, by default of the value captured from the provided <code>opening</code> indicates the type of the opening chars in generic type <code>Wrapped</code>  via return type.</p> |      |
| <p><strong><code>TextClosing extends string</code></strong></p><p>A generic type variable constrained by the <a href="https://www.typescriptlang.org/docs/handbook/basic-types.html#string"><code>string</code></a>, by default of the value captured from the provided <code>closing</code> indicates the type of the closing chars in generic type <code>Wrapped</code> via return type.</p>  |      |

### Parameters

| Name: type             | Description                                                                                                                                                                         |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `opening: TextOpening` | The **opening** chars of a generic type variable `TextOpening` to wrap the [`text`](../../wrap/instance/accessors/#wrap.prototype.text) of the [`Wrapper`](../wrapper.md) instance. |
| `closing: TextClosing` | The **closing** chars of a generic type variable `TextClosing` to wrap the [`text`](../../wrap/instance/accessors/#wrap.prototype.text) of the [`Wrapper`](../wrapper.md) instance. |

### Returns

The **return value** is the [`text`](../../wrap/instance/accessors/#wrap.prototype.text) wrapped by given `opening` and `closing` chars of generic type `Wrapped`.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
