# guardRegExp()

## `guardRegExp()`

Guards the value to be a [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/RegExp).

{% code title="guard-regexp.func.ts" %}
```typescript
const guardRegExp = <Type extends RegExp, Payload extends object>(
  value: Type,
  callback?: ResultCallback<Type, Payload>,
  payload?: Payload
): value is Type => isRegExp(value, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`RegExp`**</mark>

A generic type variable `Type` constrained by [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/RegExp) indicates captured type of the given [`value`](guardregexp.md#value-type) via the [return type](guardregexp.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardregexp.md#callback-resultcallback-less-than-bigint-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardregexp.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardregexp.md#payload-payload) optional parameter of the [`guardRegExp()`](guardregexp.md#guardregexp) function from which it captures its value.

### Parameters

#### `value: Type`

Regular expression of generic type variable [`Type`](guardregexp.md#typeextendsregexp) constrained by [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/RegExp) to guard.

#### `callback?: ResultCallback<Type, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardregexp.md#payloadextendsobject) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardregexp.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardregexp.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is Type`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](guardregexp.md#value-type) is a generic type variable [`Type`](guardregexp.md#typeextendsregexp), by default of type captured from the supplied [`value`](guardregexp.md#value-type).&#x20;

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](guardregexp.md#value-type) is a [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/RegExp).

## Example usage

```typescript
// Example usage.
import { guardRegExp } from '@angular-package/type';

guardRegExp(/^[]/); // true, value is RegExp
guardRegExp(false as any); // false, value is RegExp
```
