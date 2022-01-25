# ★ isString()

## `isString()`

Checks if any value is a `string` type by using the `isStringType()` function or an instance of `String` by using the `isStringObject()` function.

Use `isString()` or `is.string()` to check if **any** value is a \[`string`]\[js-string] type or an instance of \[`String`]\[js-string].

{% code title="is-string.func.ts" %}
```typescript
const isString = <
  Type extends AnyString = string,
  Payload extends object = object
>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Type =>
  callback(isStringType(value) || isStringObject(value), value, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`AnyString`**</mark>**`=`**<mark style="color:green;">**`string`**</mark>

A generic type variable `Type` constrained by [`AnyString`](../types/anystring.md) indicates captured [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type of the given [`value`](isstring.md#value-any) via the [return type](isstring.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](isstring.md#callback-resultcallback-less-than-any-minmax-less-than-min-max-greater-than-and-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

A generic type variable `Type` guarded by `AnyString` by default `string` indicates the type of the `value` via the return type `value is Type`.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isstring.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isstring.md#payload-payload) optional parameter of the [`isString()`](isstring.md#isstring) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isstring.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isstring.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Type`

The **return type** is a `boolean` as the result of its statement indicating the `value` is a generic type variable `Type` by default equal to the `string`.

### Returns

The return value is a `boolean` indicating whether the provided `value` is a `string` type or an instance of `String`.

The **return value** is a `boolean` indicating whether the provided `value` is a `string` type or an instance of \[`String`]\[js-string].

### Example usage

```typescript
// Example usage.
import { isString } from '@angular-package/type';

isString('age'); // true; The return type `value is string`
isString(new String('age')); // true; The return type `value is string`

// Fake string example.
const fakeString = new Number('asd');

Object.assign(fakeString, {
  get [Symbol.toStringTag](): string {
    return 'string';
  },
});

isString(fakeString); // false
typeOf(fakeString); // "string"
typeof fakeString; // "object"
```
