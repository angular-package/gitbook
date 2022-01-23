# guardSymbol()

## `guardSymbol()`

Guards the value to be a [`symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol).

{% code title="guard-symbol.func.ts" %}
```typescript
const guardSymbol = <Payload extends object>(
  value: symbol,
  callback?: ResultCallback<symbol, Payload>,
  payload?: Payload
): value is symbol => isSymbol(value, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardsymbol.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardsymbol.md#payload-payload) optional parameter of the [`guardObject()`](guardsymbol.md#guardobject) function from which it captures its value.

### Parameters

#### `value: symbol`

A [`symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol) type value to guard.

#### `callback?: ResultCallback<null, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardsymbol.md#payloadextendsobject) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardsymbol.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardsymbol.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is`<mark style="color:green;">`symbol`</mark>

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](guardsymbol.md#value-true) is a [`symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol) indicating whether the [`value`](guardsymbol.md#value-symbol) is a [`symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol).

### Example usage

```typescript
// Example usage.
import { guardSymbol } from '@angular-package/type';

const SYMBOL_NUMBER: unique symbol = Symbol(27);
const SYMBOL_STRING: unique symbol = Symbol('Twenty seven');

guardSymbol(SYMBOL_NUMBER); // true; return type `value is symbol`
guardSymbol(SYMBOL_STRING); // true; return type `value is symbol`
```
