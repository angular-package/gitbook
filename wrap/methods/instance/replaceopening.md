# ★ replaceOpening()

## `Wrap.prototype.replaceOpening()`

Returns the [primitive value](valueof.md) with replaced [`opening`](../../accessors/instance/opening.md) chars.

{% code title="wrap.class.ts" %}
```typescript
public replaceOpening<ReplaceOpening extends string = ''>(
  opening: ReplaceOpening
): `${ReplaceOpening}${Text}${Closing}` {
  return `${opening}${this.#text}${this.#closing}`;
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`ReplaceOpening`**</mark>**`extends`**<mark style="color:green;">**`string`**</mark>**`=`**<mark style="color:green;">**`''`**</mark>

A generic type variable constrained by the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string), by default of the value captured from the provided [`opening`](replaceopening.md#opening-replaceopening) indicates the `ReplaceOpening` type on the template of the [return type](replaceopening.md#return-type).

### Parameters

#### `opening: ReplaceOpening`

The opening chars of a generic type variable [`ReplaceOpening`](replaceopening.md#replaceopeningextendsstring) to replace the [`opening`](../../accessors/instance/opening.md) chars in the [primitive value](valueof.md).

### Return type

#### `${ReplaceOpening}${Text}${Closing}`

The **return type** is the [template literal](https://www.typescriptlang.org/docs/handbook/2/template-literal-types.html) of generic type variables in order [`ReplaceOpening`](replaceopening.md#replaceopeningextendsstring), [`Text`](../../generic-type-variables.md#wrap-less-than...-text-...greater-than) and [`Closing`](../../generic-type-variables.md#wrap-closing).

### Returns

The **return value** is the [primitive value](valueof.md) with replaced [`opening`](../../accessors/instance/opening.md) chars of a generic type variables in order [`ReplaceOpening`](replaceopening.md#replaceopeningextendsstring), [`Text`](../../generic-type-variables.md#wrap-less-than...-text-...greater-than) and [`Closing`](../../generic-type-variables.md#wrap-closing) on the template.

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns {{quote] of type "{{quote]".
new Wrap(`[`, `]`, 'quote').replaceOpening('{{');

// Returns {{quote] of "{{quote]".
new Wrap(``, `]`, 'quote').replaceOpening('{{');

// Returns <quote] of "<quote]".
new Wrap(``, `]`, 'quote').replaceOpening('<');
```
