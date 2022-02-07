# unwrap()

## `Wrapper.prototype.unwrap()`

Returns the [`text`](../../wrap/accessors/get-text.md) without the [`opening`](../../wrap/accessors/get-opening.md) and [`closing`](../../wrap/accessors/get-closing.md) chars.

{% code title="wrapper.class.ts" %}
```typescript
public unwrap(): Text {
  return this.text;
}
```
{% endcode %}

### Returns

The **return value** is the [`text`](../../wrap/accessors/get-text.md) of a generic type variable [`Text`](../generic-type-variables.md#wrapper-less-than...-text-...greater-than).

## Example usage

```typescript
// Example usage.wrapper
import { Wrapper } from '@angular-package/wrapper';

const longText = new Wrapper('{', '}', '{This is a long text}');

// Returns {This is a long text}.
longText.unwrap();
```
