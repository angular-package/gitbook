# valueOf()

## `Wrap.prototype.valueOf()`

Returns the [wrap](../../../getting-started/basic-concepts.md#wrap), [primitive value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/valueOf) of a specified [`Wrap`](broken-reference) object.

{% embed url="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/valueOf" %}

{% code title="wrap.class.ts" %}
```typescript
public valueOf(): `${Opening}${Text}${Closing}` {
  return super.valueOf() as `${Opening}${Text}${Closing}`;
}
```
{% endcode %}

### Return type

#### `${Opening}${Text}${Closing}`

The **return type** is the [template literal](https://www.typescriptlang.org/docs/handbook/2/template-literal-types.html) of generic type variables in order [`Opening`](../../generic-type-variables.md#wrap-opening), [`Text`](../../generic-type-variables.md#wrap-less-than...-text-...greater-than) and [`Closing`](../../generic-type-variables.md#wrap-closing).

### Returns

The **return value** is the wrap of generic type variables in order [`Opening`](../../generic-type-variables.md#wrap-opening), [`Text`](../../generic-type-variables.md#wrap-less-than...-text-...greater-than), and [`Closing`](../../generic-type-variables.md#wrap-closing) on the template.

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns [quote] of type "[quote]".
new Wrap(`[`, `]`, 'quote').valueOf();
```
