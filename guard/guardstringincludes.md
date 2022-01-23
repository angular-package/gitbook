# guardStringIncludes()

## `guardStringIncludes()`

Guards the value to be a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) that includes the specified words/sentences.

Use `guardStringIncludes()` or `guard.stringIncludes()` to guard the value to be a \[`string`]\[js-string] type or an instance of \[`String`]\[js-string] that **includes** the specified **words/sentences**.

{% code title="guard-string-includes.func.ts" %}
```typescript
const guardStringIncludes = <
  Type extends AnyString,
  Payload extends object = object
>(
  value: Type,
  includes: string[],
  callback: ResultCallback<
    Type,
    { includes: typeof includes } & Payload
  > = resultCallback,
  payload?: Payload
): value is Type => isStringIncludes(value, includes, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`AnyString`**</mark>

A generic type variable `Obj` constrained by [`AnyString`](../types/anystring.md) indicates captured [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type of the given [`value`](guardstringincludes.md#value-type) via the [return type](guardstringincludes.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardstringincludes.md#callback-resultcallback-less-than-bigint-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

A generic type variable `Type` guarded by `AnyString`, by default of value captured from the supplied `value` indicates the type of the `value` via the return type `value is Type`.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardstringincludes.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardstringincludes.md#payload-payload) optional parameter of the [`guardObject()`](guardstringincludes.md#guardobject) function from which it captures its value.

### Parameters

#### `value: Type`

The value of a generic type variable [`Type`](guardstringincludes.md#typeextendsanystring) constrained by the [`AnyString`](../types/anystring.md), by default of the type captured from itself to check against the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) that contains **words/sentences** from a given [`includes`](guardstringincludes.md#includes-string).

#### `includes: string[]`

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) as **words/sentences** to be **case-sensitive** searched for within the given [`value`](guardstringincludes.md#value-type).

#### `callback?: ResultCallback<Type, { includes: typeof includes } & Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardstringincludes.md#payloadextendsobject) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

{% hint style="info" %}
The **`payload`** parameter of given `callback` function consists of the **`includes`** property of the given [`includes`](guardstringincludes.md#includes-string), and it can't be overwritten by the given [`payload`](guardstringincludes.md#payload-payload) parameter of the main function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardstringincludes.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardstringincludes.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is Type`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](guardstringincludes.md#value-type) is a generic type variable [`Type`](guardstringincludes.md#typeextendsanystring) by default of the type captured from the [`value`](guardstringincludes.md#value-type).

### Returns

The **return value** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) indicating whether the provided [`value`](guardstringincludes.md#value-type) is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) that includes the specified **words/sentences**.

### Example usage

```typescript
// Example usage.
import { guardStringIncludes } from '@angular-package/type';

// true; The return type `value is "This is a person without age."`
guardStringIncludes('This is a person without age.', ['age']);
// false; The return type `value is "This is a person without age."`
guardStringIncludes('This is a person without age.', ['Person']);
// false; The return type `value is "This is a person without age."`
guardStringIncludes('This is a person without age.', ['age', 'Person']);
guardStringIncludes(new String('This is artificial intelligence.'), [
  'artificial',
  'intelligence',
]); // true; The return type `value is String`
```
