# ★replaceOpening()

### `Wrap.prototype.replaceOpening()`

Returns the primitive value with **replaced** **opening** chars.

{% code title="wrap.class.ts" %}
```typescript
public replaceOpening<ReplaceOpening extends string = ''>(
  opening: ReplaceOpening
): `${ReplaceOpening}${Text}${Closing}` {
  return `${opening}${this.#text}${this.#closing}`;
}
```
{% endcode %}

| Generic type variables                                                                                                                                                                                                                                                                                                                                                             |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong><code>ReplaceOpening extends string</code></strong></p><p>A generic type variable constrained by the <a href="https://www.typescriptlang.org/docs/handbook/basic-types.html#string"><code>string</code></a>, by default of the value captured from the provided <code>opening</code> indicates the <code>ReplaceOpening</code> type on template of the return type.</p> |

### Parameters

| Name: type                | Description                                                                                                        |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| `opening: ReplaceOpening` | The opening chars of a generic type variable `ReplaceOpening` to replace the opening chars in the primitive value. |

### Returns

The return value is the primitive value with replaced opening chars of a generic type variables in order `ReplaceOpening`, [`Text`](../generic-type-variables.md#wrap-less-than...-text-...greater-than) and [`Closing`](../generic-type-variables.md#wrap-closing) on the template `${ReplaceOpening}${Text}${Closing}`.

### Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns {{quote] of type "{{quote]".
new Wrap(`[`, `]`, 'quote').replaceOpening('{{');
```
