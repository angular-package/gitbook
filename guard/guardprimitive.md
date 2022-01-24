# guardPrimitive()

## `guardPrimitive()`

Guards the value to be the [`Primitive`](../types/primitive.md) type or the given [`type`](guardprimitive.md#type-primitives) of the [`Primitives`](../types/primitives.md).

Use `guardPrimitive()` or `guard.primitive()` to guard the `value` to be the `Primitive` type or the given `type` of the `Primitives`.

{% code title="guard-primitive.func.ts" %}
```typescript
const guardPrimitive = <
  Type extends Primitive,
  Payload extends object = object
>(
  value: Type,
  type?: Primitives,
  callback?: ResultCallback<Type, Payload>,
  payload?: Payload
): value is Type => isPrimitive(value, type, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`Primitive`**</mark>

A generic type variable `Type` constrained by generic type [`Primitive`](../types/primitive.md) indicates captured type of the given [`value`](guardprimitive.md#value-type) via the [return type](guardprimitive.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardprimitive.md#callback-resultcallback-less-than-bigint-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardprimitive.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardprimitive.md#payload-payload) optional parameter of the [`guardPrimitive()`](guardprimitive.md#guardprimitive) function from which it captures its value.

### Parameters

#### `value: Type`

The value of a generic type variable [`Type`](guardprimitive.md#typeextendsprimitive) constrained by the [`Primitive`](../types/primitive.md), by default of the type captured from itself to guard.

#### `type?: Primitives`

An optional specific type of [`Primitives`](../types/primitives.md) to check the given [`value`](guardprimitive.md#value-type).

#### `callback?: ResultCallback<Type, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardprimitive.md#payloadextendsobject-object) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardprimitive.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardprimitive.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is Type`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](guardprimitive.md#value-type) is [`Primitive`](../types/primitive.md), by default of type captured from the supplied [`value`](guardprimitive.md#value-obj).

### Returns

The **return value** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) indicating whether the [`value`](guardprimitive.md#value-type) is the [`Primitive`](../types/primitive.md) type or the given `type` of [`Primitives`](../types/primitives.md).

### Example usage

```typescript
// Example usage.
import { guardPrimitive } from '@angular-package/type';

// Any primitive.
guardPrimitive('x'); // true, value is 'x'
guardPrimitive(1); // true, value is 1
guardPrimitive(true), // true, value is true
guardPrimitive(undefined); // true, value is undefined
guardPrimitive(null); // true, value is null

// string.
const firstName = 'firstName';
guardPrimitive(firstName, 'string'); // true; return type `value is "firstName"`
let letFirstName = 'firstName';
guardPrimitive(letFirstName, 'string'); // true; return type `value is string`

// number.
const age = 5;
guardPrimitive(age, 'number'); // true; return type `value is 5`
let letAge = 5;
guardPrimitive(letAge, 'number'); // true; return type `value is number`

// null.
const myNull = null;
guardPrimitive(myNull, 'null'); // true; return type `value is null`

// bigint
const oldAge = 1n;
guardPrimitive(oldAge, 'bigint'); // true; return type `value is 1n`
let letOldAge = 1n;
guardPrimitive(letOldAge, 'bigint'); // true; return type `value is bigint`

// Boolean.
const question = true;
guardPrimitive(question, 'boolean'); // true; return type `value is true`
let letQuestion = true;
guardPrimitive(letQuestion, 'boolean'); // true; return type `value is true`

// Undefined.
const und = undefined;
guardPrimitive(und, 'undefined'); // true; return type `value is undefined`
let letUndefined ;
guardPrimitive(letUndefined, 'undefined'); // true; return type `value is undefined`

// Symbol.
guardPrimitive(Symbol(firstName), 'symbol'); // true; return type `value is symbol`
```
