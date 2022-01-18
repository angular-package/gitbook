# ★replaceClosing()

### `Wrap.prototype.replaceClosing()`

Returns the primitive value with **replaced** **closing** chars.

{% code title="wrap.class.ts" %}
```typescript
public replaceClosing<ReplaceClosing extends string = ''>(
  closing: ReplaceClosing
): `${Opening}${Text}${ReplaceClosing}` {
  return `${this.#opening}${this.#text}${String(closing) as ReplaceClosing}`;
}
```
{% endcode %}

| Generic type variables                                                                                                                                                                                                                                                                                                                                                             |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong><code>ReplaceClosing extends string</code></strong></p><p>A generic type variable constrained by the <a href="https://www.typescriptlang.org/docs/handbook/basic-types.html#string"><code>string</code></a>, by default of the value captured from the provided <code>closing</code> indicates the <code>ReplaceClosing</code> type on template of the return type.</p> |

### Parameters

| Name: type                | Description                                                                                                        |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| `closing: replaceClosing` | The closing chars of a generic type variable `ReplaceClosing` to replace the closing chars in the primitive value. |

### Returns

The **return value** is the primitive value with replaced closing chars of a generic type variables in order [`Opening`](../generic-type-variables.md#wrap-opening), [`Text`](../generic-type-variables.md#wrap-less-than...-text-...greater-than) and `ReplaceClosing` on the template `${Opening}${Text}${ReplaceClosing}.`

### Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/text';

// Returns [quote}} of type "[quote}}".
new Wrap(`[`, `]`, 'quote').replaceClosing('}}');
```
