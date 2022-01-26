# isPrimitive()

## `isPrimitive()`

Checks if any value is a `Primitive` type or specific type from a given `type` of the `Primitives`.

Use `isPrimitive()` or `is.primitive()` to check if **any** value is the `Primitive` type or specific type from a given `type` of the `Primitives`.

{% code title="is-primitive.func.ts" %}
```typescript
const isPrimitive = <
  Type extends Primitive,
  Payload extends object = object
>(
  value: any,
  type?: Primitives,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Type =>
  isStringType(type)
  ? {
      bigint: isBigInt,
      boolean: isBooleanType,
      number: isNumberType,
      null: isNull,
      string: isStringType,
      symbol: isSymbol,
      undefined: isUndefined,
    }[type](value, callback, payload)
  : callback(
      isNull(value) ||
        (typeof value !== 'object' && typeof value !== 'function'),
      value,
      payload
    );
```
{% endcode %}

### Generic type variables

A generic type variable `Type` constrained by the `Primitive` type indicates the type of `value` parameter via the return type `value is Type`.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isprimitive.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isprimitive.md#payload-payload) optional parameter of the [`isPrimitive()`](isprimitive.md#isprimitive) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `type?: Primitives`

An optional value of `Primitives` type indicates against which type the provided `value` is checked.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isprimitive.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isprimitive.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Type`

The **return type** is a `boolean` as the result of its statement indicating the `value` is a generic type variable `Type` by default equal to `Primitive`.

### Returns

The **return value** is a `boolean` indicating whether the provided `value` is a primitive type of the `Primitives`.

## Example usage

```typescript
// Example usage.
import { isPrimitive } from '@angular-package/type';

isPrimitive(1n); // Returns `true` as `value is Primitive`
isPrimitive<bigint>(1n, 'bigint'); // Returns `true` as `value is bigint`
isPrimitive<boolean>(false, 'boolean'); // Returns `true` as `value is boolean`
isPrimitive<number>(27, 'number'); // Returns `true` as `value is number`
isPrimitive<null>(null, 'null'); // Returns `true` as `value is null`
isPrimitive<string>('age', 'string'); // Returns `true` as `value is string`
isPrimitive<symbol>(Symbol(27), 'symbol'); // Returns `true` as `value is symbol`
isPrimitive<undefined>(undefined, 'undefined'); // Returns `true` as `value is undefined`
```
