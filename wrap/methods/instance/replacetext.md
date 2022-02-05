# ★ replaceText()

## `Wrap.prototype.replaceText()`

Returns the [primitive value](valueof.md) with replaced [`text`](../../accessors/instance/text.md).

{% code title="wrap.class.ts" %}
```typescript
public replaceText<ReplaceText extends string = ''>(
  text: ReplaceText
): `${Opening}${ReplaceText}${Closing}` {
  return `${this.#opening}${text}${this.#closing}`;
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`ReplaceText`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>**`=`**<mark style="color:green;">**`''`**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`text`](replacetext.md#text-replacetext) indicates the `ReplaceText` type on the template of the [return type](replacetext.md#return-type).

### Parameters

#### `text: ReplaceText`

The text of a generic type variable [`ReplaceText`](replacetext.md#replacetext-extends-string) to replace the [`text`](../../accessors/instance/text.md) in the [primitive value](valueof.md).

### Return type

#### `${Opening}${ReplaceText}${Closing}`

The **return type** is the [template literal](https://www.typescriptlang.org/docs/handbook/2/template-literal-types.html) of generic type variables in order [`Opening`](../../generic-type-variables.md#wrap-opening), [`ReplaceText`](replacetext.md#replacetextextendsstring) and [`Closing`](../../generic-type-variables.md#wrap-closing).&#x20;

### Returns

The **return value** is the [primitive value](valueof.md) with replaced [`text`](../../accessors/instance/text.md) of a generic type variables in order [`Opening`](../../generic-type-variables.md#wrap-opening), [`ReplaceText`](replacetext.md#replacetextextendsstring) and [`Closing`](../../generic-type-variables.md#wrap-closing) on the template.

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns [span] of type "[span]".
new Wrap(`[`, `]`, 'quote').replaceText('span');

// Returns [bold] of "[bold]".
new Wrap(`[`, `]`, '').replaceText('bold');

// Returns [u] of "[u]".
new Wrap(`[`, `]`).replaceText('u');

// Returns size] of "size]".
new Wrap(``, `]`).replaceText('size');

// Returns [size of "[size".
new Wrap(`[`, ``).replaceText('size');
```
