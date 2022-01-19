# ★replaceText()

### `Wrap.prototype.replaceText()`

Returns the primitive value with replaced [`text`](../instance-accessors/text.md).

{% code title="wrap.class.ts" %}
```typescript
public replaceText<ReplaceText extends string = ''>(
  text: ReplaceText
): `${Opening}${ReplaceText}${Closing}` {
  return `${this.#opening}${text}${this.#closing}`;
}
```
{% endcode %}

| Generic type variables                                                                                                                                                                                                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong><code>ReplaceText extends string</code></strong></p><p>A generic type variable constrained by the <a href="https://www.typescriptlang.org/docs/handbook/basic-types.html#string"><code>string</code></a>, by default of the value captured from the provided <code>text</code> indicates the <code>ReplaceText</code> type on template of the return type.</p> |

### Parameters

| Name: type          | Description                                                                                                                      |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `text: ReplaceText` | The text of a generic type variable `ReplaceText` to replace the [`text`](../instance-accessors/text.md) in the primitive value. |

### Returns

The **return value** is the primitive value with replaced [`text`](../instance-accessors/text.md) of a generic type variables in order [`Opening`](../generic-type-variables.md#wrap-opening), `ReplaceText` and [`Closing`](../generic-type-variables.md#wrap-closing) on the template `${Opening}${ReplaceText}${Closing}`.

### Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns [span] of type "[span]".
new Wrap(`[`, `]`, 'quote').replaceText('span');
```
