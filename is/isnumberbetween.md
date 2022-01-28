# isNumberBetween()

## `isNumberBetween()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type or an instance of [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number)(by using [`isNumber()`](isnumber.md)) between a specified range.

{% code title="is-number-between.func.ts" %}
```typescript
const isNumberBetween = <
  Type extends AnyNumber = number,
  Min extends number = number,
  Max extends number = number,
  Payload extends object = object
>(
  value: any,
  min: Min,
  max: Max,
  callback: ResultCallback<
    any,
    { min: Min, max: Max } & Payload
  > = resultCallback,
  payload?: Payload
): value is NumberBetween<Min, Max, Type> =>
  callback(
    isNumber(value)
      ? (isNumberType(min) ? value.valueOf() >= min : false) &&
        (isNumberType(max) ? value.valueOf() <= max : false)
      : false,
    value,
    { ...payload, min, max } as any
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Type`</mark>`extends`<mark style="color:green;">`AnyNumber`</mark>`=`<mark style="color:green;">`number`</mark>

A generic type variable `Type` constrained by [`AnyNumber`](../types/anynumber.md) indicates the number type of the given [`value`](isnumberbetween.md#value-any) via the [return type](isnumberbetween.md#return-type), by default [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number).

#### <mark style="color:green;">`Min`</mark>`extends`<mark style="color:green;">`number`</mark>`=`<mark style="color:green;">`number`</mark>

A generic type variable `Min` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type, by default of value captured from the supplied [`min`](isnumberbetween.md#min-min) indicates the **minimum** range of the provided [`value`](isnumberbetween.md#value-any) via the [return type](isnumberbetween.md#return-type) and the fixed shape of optional [`payload`](../types/resultcallback.md#payload-payload) parameter of the provided [`callback`](isnumberbetween.md#callback-resultcallback-less-than-any-min-min-max-max-and-payload-greater-than) function.

#### <mark style="color:green;">`Max`</mark>`extends`<mark style="color:green;">`number`</mark>`=`<mark style="color:green;">`number`</mark>

A generic type variable `Max` constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) type, by default of value captured from the supplied [`max`](isnumberbetween.md#max-max) indicates the **maximum** range of the provided [`value`](isnumberbetween.md#value-any) via the [return type](isnumberbetween.md#return-type) and the fixed shape of optional [`payload`](../types/resultcallback.md#payload-payload) parameter of the provided [`callback`](isnumberbetween.md#callback-resultcallback-less-than-any-min-min-max-max-and-payload-greater-than) function.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isnumberbetween.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isnumberbetween.md#payload-payload) optional parameter of the [`isNumberBetween()`](isnumberbetween.md#isnumberbetween) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `min: Min`

The **minimum** range of generic type variable [`Min`](isnumberbetween.md#minextendsnumber-number) for a given [`value`](isnumberbetween.md#value-any).

#### `max: Max`

The **maximum** range of generic type variable [`Max`](isnumberbetween.md#maxextendsnumber-number) for a given [`value`](isnumberbetween.md#value-any).

#### `callback: ResultCallback<any, { min: Min, max: Max } & Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isnumberbetween.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isnumberbetween.md#payloadextendsobject) with optional properties from the provided [`payload`](isnumberbetween.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

{% hint style="info" %}
The [`payload`](../types/resultcallback.md#payload-payload) parameter of the [`callback`](../types/resultcallback.md) function consists of the [`min`](isnumberbetween.md#min-min) and [`max`](isnumberbetween.md#max-max) properties given in parameters of the core function, and they can't be overwritten by the given [`payload`](isnumberbetween.md#payload-payload) parameter of the main function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isnumberbetween.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isnumberbetween.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is NumberBetween<Min, Max, Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isnumberbetween.md#value-any) is a generic type [`NumberBetween`](../types/numberbetween.md) that takes generic type variables [`Min`](isnumberbetween.md#minextendsnumber-number) and [`Max`](isnumberbetween.md#maxextendsnumber-number) as a **range** of the supplied [`value`](isnumberbetween.md#value-any) and [`Type`](isnumberbetween.md#typeextendsanynumber-number) as the type of the supplied [`value`](isnumberbetween.md#value-any).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](isnumberbetween.md#value-any) is a finite [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) of a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type or an instance of [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) between a specified range.

## Example usage

```typescript
// Example usage.
import { isNumberBetween } from '@angular-package/type';

const age = 13;

// true; The return type `value is NumberBetween<0, 13, number>`
isNumberBetween(age, 0, 13);
// false; The return type `value is NumberBetween<14, 28, number>`
isNumberBetween(age, 14, 28);
// false; The return type `value is NumberBetween<0, 12, number>`
isNumberBetween(age, 0, 12);
// true; The return type `value is NumberBetween<13, 13, number>`
isNumberBetween(age, 13, 13);

const ageBox = new Number(age);

// true; The return type `value is NumberBetween<0, 13, Number>`
isNumberBetween(ageBox, 0, 13);
// false; The return type `value is NumberBetween<14, 28, Number>`
isNumberBetween(ageBox, 14, 28);
// false; The return type `value is NumberBetween<0, 12, Number>`
isNumberBetween(ageBox, 0, 12);
// true; The return type `value is NumberBetween<13, 13, Number>`
isNumberBetween(ageBox, 13, 13);
```
