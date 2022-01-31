# ★ replaceClosing()

## `Wrap.prototype.replaceClosing()`

Returns the [primitive value](valueof.md) with **replaced** [`closing`](../../accessors/closing.md) chars.

{% code title="wrap.class.ts" %}
```typescript
public replaceClosing<ReplaceClosing extends string = ''>(
  closing: ReplaceClosing
): `${Opening}${Text}${ReplaceClosing}` {
  return `${this.#opening}${this.#text}${String(closing) as ReplaceClosing}`;
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`ReplaceClosing`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>**`=`**<mark style="color:green;">**`''`**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`closing`](replaceclosing.md#closing-replaceclosing) indicates the `ReplaceClosing` type on the template of the [return type](replaceclosing.md#return-type).

### Parameters

#### `closing: replaceClosing`

The closing chars of a generic type variable [`ReplaceClosing`](replaceclosing.md#replaceclosingextendsstring) to replace the [`closing`](../../accessors/closing.md) chars in the [primitive value](valueof.md).

### Return type

#### `${Opening}${Text}${ReplaceClosing}`

The **return type** is [template literal](https://www.typescriptlang.org/docs/handbook/2/template-literal-types.html) of generic type variables in order [`Opening`](../../generic-type-variables.md#wrap-opening), [`Text`](../../generic-type-variables.md#wrap-less-than...-text-...greater-than) and [`ReplaceClosing`](replaceclosing.md#replaceclosingextendsstring).

### Returns

The **return value** is the [primitive value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/valueOf) with replaced [`closing`](../../accessors/closing.md) chars of a generic type variables in order [`Opening`](../../generic-type-variables.md#wrap-opening), [`Text`](../../generic-type-variables.md#wrap-less-than...-text-...greater-than) and [`ReplaceClosing`](replaceclosing.md#replaceclosingextendsstring) on the template.

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns [quote}} of type "[quote}}".
new Wrap(`[`, `]`, 'quote').replaceClosing('}}');

// Returns [quote}} of "[quote}}".
new Wrap(`[`, ``, 'quote').replaceClosing('}}');

// Returns [quote> of "[quote>".
new Wrap(`[`, ``, 'quote').replaceClosing('>');
```
