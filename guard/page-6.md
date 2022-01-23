# guardFunction()

## `guardFunction()`

Guards the value to be a [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function).

{% code title="guard-function.func.ts" %}
```typescript
const guardFunction = <Type extends Function, Payload extends object>(
  value: Type,
  callback?: ResultCallback<Type, Payload>,
  payload?: Payload
): value is Type => isFunction(value, callback, payload);
```
{% endcode %}

Code on [**GitHub**](https://github.com/angular-package/type/blob/5.0.x/src/guard/lib/guard-function.func.ts).

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`Function`**</mark>

A generic type variable `Type` constrained by [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function) indicates captured [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function) type of the given [`value`](page-6.md#value-type) via the [return type](page-6.md#return-type) and the [`value`](../type/resultcallback.md#value-value) parameter of the provided [`callback`](page-6.md#callback-resultcallback-less-than-bigint-payload-greater-than) function [`ResultCallback`](../type/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../type/resultcallback.md#payload-payload) of the supplied [`callback`](page-6.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](page-6.md#payload-payload) optional parameter of the [`guardFunction()`](page-6.md#guardfunction) function from which it captures its value.

### Parameters

#### `value: Type`

The [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function) of a generic type variable [`Type`](page-6.md#typeextendsfunction) to guard.

#### `callback?: ResultCallback<Type, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../type/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](page-6.md#payloadextendsobject-object) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](page-6.md#payloadextendsobject-object) is assigned to the [`payload`](../type/resultcallback.md#payload-payload) of the given [`callback`](page-6.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is Type`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](page-6.md#value-type) is a generic type variable [`Type`](page-6.md#typeextendsfunction) by default equal to the type captured from the supplied [`value`](page-6.md#value-type).

### Returns

The **return value** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) indicating whether the [`value`](page-6.md#value-type) is a [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function).

### Example usage

```typescript
// Example usage.
import { guardFunction } from '@angular-package/type';

guardFunction('x'); // false value is Function
guardFunction(() => {}); // true value is () => void
guardFunction((x: number, y: number) => x + y); // true value is (x: number, y: number) => number
```
