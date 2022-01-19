# text

### `Wrap.prototype.text`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the text of the [`Wrap`](../../wrap.md) by returning the [`#text`](../properties/#text-text) property of a specified object.

{% code title="wrap.class.ts" %}
```typescript
public get text(): Text {
  return this.#text;
}
```
{% endcode %}

### Returns

The **return value** is the text of a generic type variable [`Text`](../../generic-type-variables.md#wrap-less-than...-text-...greater-than).

### Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns quote of type "quote".
new Wrap(`[`, `]`, 'quote').text;
```
