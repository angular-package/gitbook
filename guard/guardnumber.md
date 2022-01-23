# guardNumber()

## `guardNumber()`

Guards the value to be a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) of any type.

{% code title="guard-number.func.ts" %}
```typescript
const guardNumber = <
  Type extends AnyNumber,
  Payload extends object = object
>(
  value: Type,
  callback?: ResultCallback<Type, Payload>,
  payload?: Payload
): value is Type => isNumber(value, callback, payload);
```
{% endcode %}

Code on [**GitHub**](https://github.com/angular-package/type/blob/5.0.x/src/guard/lib/guard-number.func.ts).

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`AnyNumber`**</mark>

A generic type variable `Type` constrained by generic type [`AnyNumber`](../types/anynumber.md) indicates captured [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type of the given [`value`](guardnumber.md#value-type) via the [return type](guardnumber.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardnumber.md#callback-resultcallback-less-than-bigint-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardnumber.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardnumber.md#payload-payload) optional parameter of the [`guardNumber()`](guardnumber.md#guardnumber) function from which it captures its value.

### Parameters

#### `value: Type`

The value of generic type variable [`Type`](guardnumber.md#typeextendsanynumber) to guard.

#### `callback?: ResultCallback<Type, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardnumber.md#payloadextendsobject-object) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardnumber.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardnumber.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is Type`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](guardnumber.md#value-type) is a generic type variable [`Type`](guardnumber.md#typeextendsanynumber) by default of type captured from the supplied [`value`](guardnumber.md#value-type).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](guardnumber.md#value-type) is a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean).

### Example usage

```typescript
// Example usage.
import { guardNumber } from '@angular-package/type';

guardNumber(3); // true, value is number
guardNumber(3.14); // true, value is number
guardNumber(3.500); // true, value is number
guardNumber(Infinity); // false, value is number
guardNumber(NaN); // false, value is number

guardNumber(new Number(3)); // true, value is Number
guardNumber(new Number(3.14)); // true, value is Number
guardNumber(new Number(3.500)); // true, value is Number
guardNumber(new Number(Infinity)); // false, value is Number
guardNumber(new Number(NaN)); // false, value is Number
```
