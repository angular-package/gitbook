# isType()

## `isType()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is the type from a given [`type`](istype.md#type-types-less-than-t-greater-than) of the generic type [`Types`](../types/types.md).

{% code title="is-type.func.ts" %}
```typescript
const isType = <T extends Type, Payload extends object = object>(
  value: any,
  type: Types<T>,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is T =>
  isStringType(type)
  ? {
      bigint: isBigInt,
      boolean: isBooleanType,
      function: isFunction,
      number: isNumberType,
      object: isObject,
      null: isNull,
      string: isStringType,
      symbol: isSymbol,
      undefined: isUndefined,
    }[type as Primitives](value, callback, payload)
  : isNotNull(type)
  ? isInstance(value, type, callback, payload)
  : false;
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`T`**</mark>**`extends`**<mark style="color:green;">**`Type`**</mark>

A generic type variable `T` constrained by the generic type [`Type`](../types/type.md) indicates the type of [`value`](istype.md#value-any) parameter via the [return type](istype.md#return-type) `value is T` and captured type of the generic type [`Constructor`](../types/constructor.md) of the supplied [`type`](istype.md#type-types-less-than-t-greater-than).

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](istype.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](istype.md#payload-payload) optional parameter of the [`isType()`](istype.md#istype) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check against the type of given [`type`](istype.md#type-types-less-than-t-greater-than) of [`Types`](../types/types.md).

#### `type: Types<T>`

A value of the generic type [`Types`](../types/types.md) indicates against which type the provided [`value`](istype.md#value-any) is checked.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](istype.md#payloadextendsobject-object) with optional properties from the provided [`payload`](istype.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](istype.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](istype.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is T`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](istype.md#value-any) is a generic type variable [`T`](istype.md#textendstype) by default equal to the [`Type`](../types/type.md) but captured type [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global\_attributes/class) of the supplied [`type`](istype.md#type-types-less-than-t-greater-than) changes it to the class name.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](istype.md#value-any) is a type from a given [`type`](istype.md#type-types-less-than-t-greater-than) of the [`Types`](../types/types.md).

## Example usage

```typescript
// Example usage.
import { isType } from '@angular-package/type';

class Person {}
const person = new Person();

// Primitives.
isType<bigint>(1n, 'bigint'); // Returns `true` as `value is bigint`
isType<boolean>(false, 'boolean'), // Returns `true` as `value is boolean`
isType<number>(27, 'number'); // Returns `true` as `value is number`
isType<null>(null, 'null'); // Returns `true` as `value is null`
isType<string>('age', 'string'); // Returns `true` as `value is string`
isType<symbol>(Symbol(27), 'symbol'); // Returns `true` as `value is symbol`
isType<undefined>(undefined, 'undefined'); // Returns `true` as `value is undefined`
// Function.
isType<Function>(() => {}, 'function'); // Returns `true` as `value is function`
// Object.
isType<object>({}, 'object'); // Returns `true` as `value is object`
// Class.
isType(person, Person); // Returns `true` as `value is Person`
// Class with callback and payload.
isType(person, Person, (result, value, payload) => {
  value // Person {}
  /*
  payload {
    value: {},
    id: 15,
    database: 'Persons'
  }
  */
  return result;
}, { id: 15, database: 'Persons' }); // Returns `true` as `value is Person`
```
