# ★ Constructor

## `Wrap()`

Creates a new [`Wrap`](broken-reference) instance of the [`opening`](constructor.md#opening-opening) and [`closing`](constructor.md#closing-closing) chars and optional [`text`](constructor.md#text-text) to wrap.&#x20;

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

#### `opening:`[<mark style="color:green;">`Opening`</mark>](generic-type-variables.md#wrap-opening)<mark style="color:green;">``</mark>

Opening characters of the generic type variable [`Opening`](generic-type-variables.md#wrap-opening) placed before the given [`text`](constructor.md#text-text). An empty [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) indicates that for the [`hasOpening()`](methods/instance/hasopening.md#wrap.prototype.hasopening) and [`isWrapped()`](methods/instance/iswrapped.md) methods, the [`opening`](accessors/opening.md) chars are [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined), returning `false`.

#### `closing:`[<mark style="color:green;">`Closing`</mark>](generic-type-variables.md#wrap-closing)<mark style="color:green;">``</mark>

Closing characters of the generic type variable [`Closing`](generic-type-variables.md#wrap-closing) placed after the given [`text`](constructor.md#text-text). An empty [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) indicates that for the [`hasClosing()`](methods/instance/hasclosing.md) and [`isWrapped()`](methods/instance/iswrapped.md) methods, the [`closing`](accessors/closing.md) chars are [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined), returning `false`.

#### `text:`[<mark style="color:green;">`Text`</mark>](generic-type-variables.md#wrap-less-than...-text-...greater-than)`=`<mark style="color:green;">`''`</mark>

An optional text placed between the given [`opening`](constructor.md#opening-opening) and [`closing`](constructor.md#closing-closing) chars on the [template literal](https://www.typescriptlang.org/docs/handbook/2/template-literal-types.html) `${Opening}${Text}${Closing}`.

### Returns

The **return value** is a new instance of [`Wrap`](broken-reference) with the [primitive value](methods/instance/valueof.md) of the provided [`opening`](constructor.md#opening-opening), [`closing`](constructor.md#closing-closing), and the optional [`text`](constructor.md#text-text).

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns Wrap{'[]'}
new Wrap('[', ']');

// Returns Wrap{'nullnull'}
new Wrap(null as any, null as any);
```
