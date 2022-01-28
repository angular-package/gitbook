# isStringLength()

## `isStringLength()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) value is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)(by using [`isString()`](isstring.md)) of a specified length.

{% code title="is-string-length.func.ts" %}
```typescript
const isStringLength = <
  Type extends AnyString = string,
  Length extends number = number,
  Payload extends object = object
>(
  value: any,
  length: Length,
  callback: ResultCallback<any, { length: Length } & Payload> = resultCallback,
  payload?: Payload
): value is StringOfLength<Length, Length, Type> =>
  callback(
    isString(value) && isNumberType(length) && length > 0
      ? value.valueOf().length === length
      : false,
    value,
    { ...payload, length } as any
  );

```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`AnyString`**</mark>**`=`**<mark style="color:green;">**`string`**</mark>

A generic type variable `Type` constrained by [`AnyString`](../types/anystring.md) indicates the [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type of the given [`value`](isstringlength.md#value-any) via the [return type](isstringlength.md#return-type).

#### <mark style="color:green;">**`Length`**</mark>**`extends`**<mark style="color:green;">**`number`**</mark>

A generic type variable `Length` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type, by default of value captured from the supplied [`length`](isstringlength.md#length-length) indicates the **length** of the provided [`value`](isstringlength.md#value-any) via the [return type](isstringlength.md#return-type) and the fixed shape of optional [`payload`](../types/resultcallback.md#payload-payload) parameter of the provided [`callback`](isstringlength.md#callback-resultcallback-less-than-any-min-min-max-max-and-payload-greater-than) function.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isstringlength.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isstringlength.md#payload-payload) optional parameter of the [`isStringLength()`](isstringlength.md#isstringlength) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `length: Length`

The **length** of generic type variable [`Length`](isstringlength.md#lengthextendsnumber) of a given [`value`](isstringlength.md#value-any).

#### `callback: ResultCallback<any, { length: Length } & Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isstringlength.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](../types/resultcallback.md#payload-object) with optional properties from the provided [`payload`](isstringlength.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

{% hint style="info" %}
The [`payload`](../types/resultcallback.md#payload-payload) parameter of the [`callback`](../types/resultcallback.md) function consists of the [`length`](isstringlength.md#length-length) property given in parameter of the core function, and it can't be overwritten by the given [`payload`](isstringlength.md#payload-payload) parameter of the core function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isstringlength.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isstringlength.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is StringOfLength<Length, Length, Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isstringlength.md#value-any) is a generic type [`StringOfLength`](../types/stringoflength.md) that takes generic type variables [`Min`](isstringlength.md#minextendsnumber) and [`Max`](isstringlength.md#maxextendsnumber) as the **length** of the supplied [`value`](isstringlength.md#value-any), and generic type variable [`Type`](isstringlength.md#typeextendsanystring) as the type of the supplied [`value`](isstringlength.md#value-any).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isstringlength.md#value-any) is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) of the specified length.

## Example usage

```typescript
// Example usage.
import { isStringLength } from '@angular-package/type';

const firstName = 'my first name';

// true; The return type `value is StringOfLength<0, 13>`
isStringLength(firstName, 12);
// false; The return type `value is StringOfLength<0, 13>`
isStringLength(firstName, 0, 12);

// true; The return type `value is StringOfLength<0, 13>`
isStringLength(firstName, 0, 13);
// false; The return type `value is StringOfLength<14, 28>`
isStringLength(firstName, 14, 28);
// false; The return type `value is StringOfLength<0, 12>`
isStringLength(firstName, 0, 12);
// true; The return type `value is StringOfLength<13, 13>`
isStringLength(firstName, 13, 13 );

const firstNameBox = new String(firstName);

// true; The return type `value is StringOfLength<0, 13>`
isStringLength(firstNameBox, 0, 13);
// false; The return type `value is StringOfLength<14, 28>`
isStringLength(firstNameBox, 14, 28);
// false; The return type `value is StringOfLength<0, 12>`
isStringLength(firstNameBox, 0, 12);
// true; The return type `value is StringOfLength<13, 13>`
isStringLength(firstNameBox, 13, 13);
```
