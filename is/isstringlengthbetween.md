# isStringLengthBetween()

## `isStringLengthBetween()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) value is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) by using [`isString()`](isstring.md) of length within the specified range.

{% code title="is-string-length-between.func.ts" %}
```typescript
const isStringLengthBetween = <
  Type extends AnyString = string,
  Min extends number = number,
  Max extends number = number,
  Payload extends object = object
>(
  value: any,
  min: Min,
  max: Max,
  callback: ResultCallback<
    any,
    { min: Min; max: Max } & Payload
  > = resultCallback,
  payload?: Payload
): value is StringOfLength<Min, Max, Type> =>
  callback(
    isString(value)
      ? (isNumberType(min) && min >= 0
          ? value.valueOf().length >= min
          : false) &&
          (isNumberType(max) && max >= 0
            ? value.valueOf().length <= max
            : false)
      : false,
    value,
    { ...payload, min, max } as any
  );
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/is/lib/is-string-length-between.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`AnyString`**</mark>**`=`**<mark style="color:green;">**`string`**</mark>

A generic type variable `Type` constrained by [`AnyString`](../types/anystring.md) indicates [`string`](https://www.typescriptlang.org/docs/handbook/basic-types.html#string) type of the given [`value`](isstringlengthbetween.md#value-any) via the [return type](isstringlengthbetween.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](isstringlengthbetween.md#callback-resultcallback-less-than-any-min-min-max-max-and-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Min`**</mark>**`extends`**<mark style="color:green;">**`number`**</mark>

A generic type variable `Min` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type, by default of value captured from the supplied [`min`](isstringlengthbetween.md#min-max) indicates the **minimum** length of the provided [`value`](isstringlengthbetween.md#value-any) via the [return type](isstringlengthbetween.md#return-type) and the fixed shape of optional [`payload`](../types/resultcallback.md#payload-payload) parameter of the provided [`callback`](isstringlengthbetween.md#callback-resultcallback-less-than-type-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Max`**</mark>**`extends`**<mark style="color:green;">**`number`**</mark>

A generic type variable `Max` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type, by default of value captured from the supplied [`max`](isstringlengthbetween.md#max-max) indicates the **maximum** length of the provided [`value`](isstringlengthbetween.md#value-any) via the [return type](isstringlengthbetween.md#return-type) and the fixed shape of optional [`payload`](../types/resultcallback.md#payload-payload) parameter of the provided [`callback`](isstringlengthbetween.md#callback-resultcallback-less-than-type-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md).&#x20;

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isstringlengthbetween.md#callback-resultcallback-less-than-any-min-min-max-max-and-payload-greater-than) function and [`payload`](isstringlengthbetween.md#payload-payload) optional parameter of the [`isStringLength()`](isstringlengthbetween.md#isstringlength) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `min: Max`

The **minimum** length of generic type variable [`Min`](isstringlengthbetween.md#minextendsnumber) for a given [`value`](isstringlengthbetween.md#value-any).

#### `max: Max`

The **maximum** length of generic type variable [`Max`](isstringlengthbetween.md#maxextendsnumber) for a given [`value`](isstringlengthbetween.md#value-any).

#### `callback: ResultCallback<any, { min: Min, max: Max } & Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isstringlengthbetween.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isstringlengthbetween.md#payloadextendsobject-object) with optional properties from the provided [`payload`](isstringlengthbetween.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

{% hint style="info" %}
The [`payload`](../types/resultcallback.md#payload-payload) parameter of the [`callback`](isstringlengthbetween.md#callback-resultcallback-less-than-any-min-min-max-max-and-payload-greater-than) function consists of the [`min`](isstringlengthbetween.md#min-max) and [`max`](isstringlengthbetween.md#max-max) properties given in parameters of the core function, and they can't be overwritten by the given [`payload`](isstringlengthbetween.md#payload-payload) parameter of the core function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isstringlengthbetween.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isstringlengthbetween.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is StringOfLength<Min, Max, Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isstringlengthbetween.md#value-any) is a generic type [`StringOfLength`](../types/stringoflength.md) that takes generic type variables [`Min`](isstringlengthbetween.md#minextendsnumber) and [`Max`](isstringlengthbetween.md#maxextendsnumber) as the **length** of the supplied [`value`](isstringlengthbetween.md#value-any), and generic type variable [`Type`](isstringlengthbetween.md#typeextendsanystring) as the type of the supplied [`value`](isstringlengthbetween.md#value-any).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isstringlengthbetween.md#value-any) is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) of length within the specified range.

## Example usage

### `string` type

```typescript
// Example usage.
import { isStringLengthBetween } from '@angular-package/type';

const firstName = 'my first name';

// true; The return type `value is StringOfLength<0, 13, string>`
isStringLengthBetween(firstName, 0, 13);
// false; The return type `value is StringOfLength<0, 12, string>`
isStringLengthBetween(firstName, 0, 12);
v// false; The return type `value is StringOfLength<14, 28, string>`
isStringLengthBetween(firstName, 14, 28);
// true; The return type `value is StringOfLength<13, 13, string>`
isStringLengthBetween(firstName, 13, 13 ); 
```

### `String` instance

```typescript
// Example usage.
import { isStringLengthBetween } from '@angular-package/type';

const firstName = 'my first name';
const firstNameBox = new String(firstName);

// true; The return type `value is StringOfLength<0, 13, string>`
isStringLengthBetween(firstNameBox, 0, 13);
// false; The return type `value is StringOfLength<0, 12, string>`
isStringLengthBetween(firstNameBox, 0, 12);
// false; The return type `value is StringOfLength<14, 28, string>`
isStringLengthBetween(firstNameBox, 14, 28);
// true; The return type `value is StringOfLength<13, 13, string>`
isStringLengthBetween(firstNameBox, 13, 13);
```
