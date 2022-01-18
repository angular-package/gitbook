# ★ Wrap() constructor

## `Wrap()`

Creates a new [`Wrap`](wrap.md) instance of the opening and closing chars and optional text to wrap.

{% code title="wrap.class.ts" %}
```typescript
constructor(opening: Opening, closing: Closing, text: Text = '' as Text) {
  super(`${opening}${text}${closing}`);
  this.#closing = String(closing) as Closing;
  this.#text = String(text) as Text;
  this.#opening = String(opening) as Opening;
}
```
{% endcode %}

#### Parameters

| Name: type         | Description                                                                                                                         |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------- |
| `opening: Opening` | Opening characters of the generic type variable [`Opening`](generic-type-variables.md#wrap-opening) placed before the given `text`. |
| `closing: Closing` | Closing characters of the generic type variable [`Closing`](generic-type-variables.md#wrap-closing) placed after the given `text`.  |
| `text: Text = ''`  | An optional text placed between the given `opening` and `closing` chars on the template `${Opening}${Text}${Closing}`.              |

#### Returns

The **return value** is a new instance of [`Wrap`](wrap.md) with the primitive value of the provided `opening`, `closing`, and the optional `text`.

#### Usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/text';

// Returns Wrap{'[]'}
new Wrap('[', ']');

// Returns Wrap{'nullnull'}
new Wrap(null as any, null as any);
```
