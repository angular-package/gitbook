# ★ Constructor

## `Wrap()`

Creates a new [`Wrap`](info/) instance of the [`opening`](constructor.md#opening-opening) and [`closing`](constructor.md#closing-closing) chars and optional [`text`](constructor.md#text-text) to wrap.

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

### Parameters

#### `opening: Opening`

Opening characters of the generic type variable [`Opening`](generic-type-variables.md#wrap-opening) placed before the given [`text`](constructor.md#text-text).

#### `closing: Closing`

Closing characters of the generic type variable [`Closing`](generic-type-variables.md#wrap-closing) placed after the given [`text`](constructor.md#text-text).

#### `text: Text = ''`

An optional text placed between the given [`opening`](constructor.md#opening-opening) and [`closing`](constructor.md#closing-closing) chars on the [template literal](https://www.typescriptlang.org/docs/handbook/2/template-literal-types.html) `${Opening}${Text}${Closing}`.

### Returns

The **return value** is a new instance of [`Wrap`](info/) with the primitive value of the provided [`opening`](constructor.md#opening-opening), [`closing`](constructor.md#closing-closing), and the optional [`text`](constructor.md#text-text).

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns Wrap{'[]'}
new Wrap('[', ']');

// Returns Wrap{'nullnull'}
new Wrap(null as any, null as any);
```
