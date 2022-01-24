# guardStringIncludesSome()

## `guardStringIncludesSome()`

Guards the value to be a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) that **includes** **some** of the specified **words/sentences**.

{% code title="guard-string-includes-some.func.ts" %}
```typescript
const guardStringIncludesSome = <
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
): value is Type => isStringIncludesSome(value, includes, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`AnyString`**</mark>

A generic type variable `Obj` constrained by [`AnyString`](../types/anystring.md) indicates captured [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type of the given [`value`](guardstringincludessome.md#value-type) via the [return type](guardstringincludessome.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardstringincludessome.md#callback-resultcallback-less-than-bigint-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardstringincludessome.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardstringincludessome.md#payload-payload) optional parameter of the [`guardStringIncludesSome()`](guardstringincludessome.md#guardstringincludessome) function from which it captures its value.

### Parameters

#### `value: Type`

The value of a generic type variable [`Type`](guardstringincludessome.md#typeextendsanystring) constrained by the [`AnyString`](../types/anystring.md), by default of the type captured from itself to check against the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) that contains **some** of the **words/sentences** from a given [`includes`](guardstringincludessome.md#includes-string).

#### `includes: string[]`

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) as **words/sentences** to be **case-sensitive** searched for within a given [`value`](guardstringincludessome.md#value-type).

#### `callback?: ResultCallback<Type, { includes: typeof includes } & Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardstringincludessome.md#payloadextendsobject) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

{% hint style="info" %}
The **`payload`** parameter of given [`callback`](guardstringincludessome.md#callback-resultcallback-less-than-type-includes-typeof-includes-and-payload-greater-than) function consists of the **`includes`** property of the given [`includes`](guardstringincludessome.md#includes-string), and it can't be overwritten by the given [`payload`](guardstringincludessome.md#payload-payload) parameter of the main function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardstringincludessome.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardstringincludessome.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is Type`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](guardstringincludessome.md#value-type) is a generic type variable [`Type`](guardstringincludessome.md#typeextendsanystring) by default of the type captured from the [`value`](guardstringincludessome.md#value-type).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](guardstringincludessome.md#value-type) is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) that includes **some** of the specified **words/sentences**.

### Example usage

```typescript
// Example usage.
import { guardStringIncludesSome } from '@angular-package/type';

// true; The return type `value is "This is a person without age."`
guardStringIncludesSome('This is a person without age.', ['age']);
// false; The return type `value is "This is a person without age."`
guardStringIncludesSome('This is a person without age.', ['Person']);
// true; The return type `value is "This is a person without age."`
guardStringIncludesSome('This is a person without age.', ['age', 'Person']);
// true; The return type `value is String`
guardStringIncludesSome(new String('This is artificial intelligence.'), [
'artificial',
'intelligence',
]);
```
