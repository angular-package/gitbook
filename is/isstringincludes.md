# isStringIncludes()

## `isStringIncludes()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) value is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) by using [`isString()`](isstring.md) that includes all of the specified **words/sentences**.

{% code title="is-string-includes.func.ts" %}
```typescript
const isStringIncludes = <
  Type extends AnyString = string,
  Payload extends object = object
>(
  value: any,
  includes: string[],
  callback: ResultCallback<
    any,
    { includes: typeof includes } & Payload
  > = resultCallback,
  payload?: Payload
): value is Type =>
  callback(
    isString(value)
      ? isArray(includes)
        ? includes.every((include) => value.valueOf().includes(include))
        : false
      : false,
    value,
    { ...payload, includes } as any
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`AnyString`**</mark>**`=`**<mark style="color:green;">**`string`**</mark>

A generic type variable `Type` constrained by generic type [`AnyString`](../types/anystring.md) indicates captured [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type of the given [`value`](isstringincludes.md#value-any) via the [return type](isstringincludes.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](isstringincludes.md#callback-resultcallback-less-than-any-minmax-less-than-min-max-greater-than-and-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isstringincludes.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isstringincludes.md#payload-payload) optional parameter of the [`isStringIncludes()`](isstringincludes.md#isstringincludes) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check against the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) that contains **words/sentences** from a given [`includes`](isstringincludes.md#includes-string).

#### `includes: string[]`

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) as **words/sentences** to be **case-sensitive** searched for within the given [`value`](isstringincludes.md#value-any).

#### `callback: ResultCallback<any, { includes: typeof includes } & Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isstringincludes.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isstringincludes.md#payloadextendsobject) with optional properties from the provided [`payload`](isstringincludes.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isstringincludes.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isstringincludes.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Type`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isstringincludes.md#value-any) is a generic type variable [`Type`](isstringincludes.md#typeextendsanystring-string) by default equal to the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isstringincludes.md#value-any) is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) that includes all of the specified **words/sentences**.

## Example usage

```typescript
// Example usage.
import { isStringIncludes } from '@angular-package/type';

isStringIncludes('This is a person without age.', ['age']); // true; The return type `value is string`
isStringIncludes('This is a person without age.', ['Person']); // false; The return type `value is string`
isStringIncludes('This is a person without age.', ['age', 'Person']); // false; The return type `value is string`
isStringIncludes(new String('This is artificial intelligence.'), [
  'artificial',
  'intelligence',
]); // true; The return type `value is string`
```
