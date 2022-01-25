# isStringLength()

## `isStringLength()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) value is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) by using [`isString()`](isstring.md) of length within the specified range.

{% code title="is-string-length.func.ts" %}
```typescript
const isStringLength = <
  Type extends AnyString = string,
  Min extends number = number,
  Max extends number = number,
  Payload extends object = object
>(
  value: any,
  min?: Min,
  max?: Max,
  callback: ResultCallback<any, MinMax<Min, Max> & Payload> = resultCallback,
  payload?: Payload
): value is StringOfLength<Min, Max, Type> =>
  callback(
    isString(value)
    ? (isNumberType(min) && min >= 0 ? value.valueOf().length >= min : true) &&
      (isNumberType(max) && max >= 0 ? value.valueOf().length <= max : true)
    : false,
    value,
    { ...payload, min, max } as Payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`AnyString`**</mark>**`=`**<mark style="color:green;">**`string`**</mark>

A generic type variable `Type` constrained by [`AnyString`](../types/anystring.md) indicates captured [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type of the given [`value`](isstringlength.md#value-any) via the [return type](isstringlength.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](isstringlength.md#callback-resultcallback-less-than-any-minmax-less-than-min-max-greater-than-and-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Min`**</mark>**`extends`**<mark style="color:green;">**`number`**</mark>

A generic type variable `Min` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type, by default of value captured from optional [`min`](isstringlength.md#min-max) indicates the [`payload`](../types/resultcallback.md#payload-payload) parameter type of the provided [`callback`](isstringlength.md#callback-resultcallback-less-than-type-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type and the **minimum** length of the provided [`value`](isstringlength.md#value-any) via the [return type](isstringlength.md#return-type).

#### <mark style="color:green;">**`Max`**</mark>**`extends`**<mark style="color:green;">**`number`**</mark>

A generic type variable `Max` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type, by default of value captured from optional [`max`](isstringlength.md#max-max) indicates the [`payload`](../types/resultcallback.md#payload-payload) parameter type of the provided [`callback`](isstringlength.md#callback-resultcallback-less-than-type-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type and the **maximum** length of the provided [`value`](isstringlength.md#value-any) via the [return type](isstringlength.md#return-type).

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isstringlength.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isstringlength.md#payload-payload) optional parameter of the [`isStringLength()`](isstringlength.md#isstringlength) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `min?: Max`

The optional **minimum** length of generic type variable [`Min`](isstringlength.md#minextendsnumber) for a given [`value`](isstringlength.md#value-any).

#### `max?: Max`

The optional **maximum** length of generic type variable [`Max`](isstringlength.md#maxextendsnumber) for a given [`value`](isstringlength.md#value-any).

#### `callback: ResultCallback<any, MinMax<Min, Max> & Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isstringlength.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isstringlength.md#payloadextendsobject) with optional properties from the provided [`payload`](isstringlength.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

{% hint style="info" %}
The [`payload`](../types/resultcallback.md#payload-payload) parameter of the [`callback`](isstringlength.md#callback-resultcallback-less-than-any-minmax-less-than-min-max-greater-than-and-payload-greater-than) function consists of the [`min`](isstringlength.md#min-max) and [`max`](isstringlength.md#max-max) properties given in parameters of the core function, and they can't be overwritten by the given [`payload`](isstringlength.md#payload-payload) parameter of the core function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isstringlength.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isstringlength.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is StringOfLength<Min, Max, Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isstringlength.md#value-any) is a generic type [`StringOfLength`](../types/stringoflength.md) that takes generic type variables [`Min`](isstringlength.md#minextendsnumber) and [`Max`](isstringlength.md#maxextendsnumber) as the **length** of the supplied [`value`](isstringlength.md#value-any), and generic type variable [`Type`](isstringlength.md#typeextendsanystring) as the type of the supplied [`value`](isstringlength.md#value-any).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isstringlength.md#value-any) is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) of length within the specified range.

### Example usage

```typescript
// Example usage.
import { isStringLength } from '@angular-package/type';

const firstName = 'my first name';

isStringLength(firstName, 12); // true; The return type `value is StringOfLength<0, 13>`
isStringLength(firstName, 0, 12); // false; The return type `value is StringOfLength<0, 13>`

isStringLength(firstName, 0, 13); // true; The return type `value is StringOfLength<0, 13>`
isStringLength(firstName, 14, 28); // false; The return type `value is StringOfLength<14, 28>`
isStringLength(firstName, 0, 12); // false; The return type `value is StringOfLength<0, 12>`
isStringLength(firstName, 13, 13 ); // true; The return type `value is StringOfLength<13, 13>`

const firstNameBox = new String(firstName);

isStringLength(firstNameBox, 0, 13); // true; The return type `value is StringOfLength<0, 13>`
isStringLength(firstNameBox, 14, 28); // false; The return type `value is StringOfLength<14, 28>`
isStringLength(firstNameBox, 0, 12); // false; The return type `value is StringOfLength<0, 12>`
isStringLength(firstNameBox, 13, 13); // true; The return type `value is StringOfLength<13, 13>`
```
