# isStringIncludesSome()

## `isStringIncludesSome()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) value is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) by using [`isString()`](isstring.md) that includes some of the specified **words/sentences**.

{% code title="is-string-inludes-some.func.ts" %}
```typescript
const isStringIncludesSome = <
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
        ? includes.some((include) => value.valueOf().includes(include))
        : false
      : false,
    value,
    { ...payload, includes } as any
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`AnyString`**</mark>**`=`**<mark style="color:green;">**`string`**</mark>

A generic type variable `Type` constrained by [`AnyString`](../types/anystring.md) indicates captured [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type of the given [`value`](isstringincludessome.md#value-any) via the [return type](isstringincludessome.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](isstringincludessome.md#callback-resultcallback-less-than-any-minmax-less-than-min-max-greater-than-and-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isstringincludessome.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isstringincludessome.md#payload-payload) optional parameter of the [`isStringIncludesSome()`](isstringincludessome.md#isstringincludessome) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check against the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) that [`includes`](isstringincludessome.md#includes-string) **some** of the **words/sentences**.

#### `includes: string[]`

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) as **words/sentences** to be **case-sensitive** searched for within a given [`value`](isstringincludessome.md#value-any).

#### `callback: ResultCallback<any, { includes: typeof includes } & Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isstringincludessome.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isstringincludessome.md#payloadextendsobject) with optional properties from the provided [`payload`](isstringincludessome.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isstringincludessome.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isstringincludessome.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Type`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isstringincludessome.md#value-any) is a generic type variable [`Type`](isstringincludessome.md#typeextendsanystring-string) by default [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isstringincludessome.md#value-any) is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) that includes some of the specified **words/sentences**.

### Example usage

```typescript
// Example usage.
import { isStringIncludesSome } from '@angular-package/type';

isStringIncludesSome('This is a person without age.', ['age']); // true; The return type `value is string`
isStringIncludesSome('This is a person without age.', ['Person']); // false; The return type `value is string`
isStringIncludesSome('This is a person without age.', ['age', 'Person']); // true; The return type `value is string`
isStringIncludesSome(new String('This is artificial intelligence.'), [
  'artificial',
  'intelligence',
]); // true; The return type `value is string`
```
