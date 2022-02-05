# getText()

## `Wrap.prototype.getText()`

Gets the text of the wrap by returning the [`#text`](../../properties/instance/text.md) property of a specified object, without the [opening](../../accessors/instance/opening.md) and [closing](../../accessors/instance/closing.md) chars of the [`Wrap`](broken-reference).

{% code title="wrap.class.ts" %}
```typescript
public getText(): Text {
  return this.#text;
}
```
{% endcode %}

### Returns

The **return value** is the [`text`](../../accessors/instance/text.md) of a generic type variable [`Text`](../../generic-type-variables.md#wrap-less-than...-text-...greater-than).

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns quote of type "quote".
new Wrap(`[`, `]`, 'quote').getText();
```
