# getText()

### `Wrap.prototype.getText()`

Gets the text of the wrap by returning the [`#text`](../instance-properties.md#text-text) property of a specified object, without the [opening](../instance-accessors/#wrap.prototype.opening) and [closing](../instance-accessors/#wrap.prototype.closing) chars of the [`Wrap`](../wrap.md).

{% code title="wrap.class.ts" %}
```typescript
public getText(): Text {
  return this.#text;
}
```
{% endcode %}

### Returns

The **return value** is the text of a generic type variable [`Text`](../generic-type-variables.md#wrap-less-than...-text-...greater-than).

### Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns quote of type "quote".
new Wrap(`[`, `]`, 'quote').getText();
```
