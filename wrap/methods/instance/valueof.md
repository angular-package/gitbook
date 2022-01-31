# valueOf()

### `Wrap.prototype.valueOf()`

Returns the [wrap](../../../library/basic-concepts.md#wrap), primitive value of a specified [`Wrap`](../../info/) object.

{% code title="wrap.class.ts" %}
```typescript
public valueOf(): `${Opening}${Text}${Closing}` {
  return super.valueOf() as `${Opening}${Text}${Closing}`;
}
```
{% endcode %}

### Returns

The **return value** is the wrap of generic type variables in order [`Opening`](../../generic-type-variables.md#wrap-opening), [`Text`](../../generic-type-variables.md#wrap-less-than...-text-...greater-than), and [`Closing`](../../generic-type-variables.md#wrap-closing) on the template `${Opening}${Text}${Closing}`.

### Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns [quote] of type "[quote]".
new Wrap(`[`, `]`, 'quote').valueOf();
```
