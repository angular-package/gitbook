# isNotNumber()

## `isNotNumber()`

Checks if the [`value`](isnotnumber.md#value-type) is **not** the type obtained from its [object class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/toString#using\_tostring\_to\_detect\_object\_class) equal to `'number'`, not a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type and not an instance of [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number).

{% code title="is-not-number.func.ts" %}
```typescript
const isNotNumber = <Type, Payload extends object = object>(
  value: Type,
  callback: ResultCallback<Type, Payload> = resultCallback,
  payload?: Payload
): value is Never<AnyNumber, Type> =>
  callback(
    typeOf(value) !== 'number' &&
    typeof value !== 'number' &&
    value instanceof Number === false,
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>

A generic type variable `Type` indicates the captured type of the given [`value`](isnotnumber.md#value-type) via the [return type](isnotnumber.md#return-type) `value is Never<AnyNumber, Type>` and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](isnotnumber.md#callback-resultcallback-less-than-type-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isnotnumber.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](isnotnumber.md#payload-payload) optional parameter of the [`isNotNumber()`](isnotnumber.md#isnotnull) function from which it captures its value.

### Parameters

#### `value: Type`

The `value` of generic type variable [`Type`](isnotnumber.md#type), by default of the type captured from itself to check.

#### `callback: ResultCallback<Type, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isnotnumber.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isnotnumber.md#payloadextendsobject-object) with optional properties from the provided [`payload`](isnotnumber.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isnotnumber.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isnotnumber.md#callback-resultcallback-less-than-type-payload-greater-than) function.

### Return type

#### `value is Never<AnyNumber, Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isnotnumber.md#value-type) is a generic type [`Never`](../types/never.md) that takes a generic type variable [`Type`](isnotnumber.md#type) from the supplied [`value`](isnotnumber.md#value-type) and **not** equal to [`AnyNumber`](../types/anynumber.md), which makes it [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never) [`AnyNumber`](../types/anynumber.md) but of type captured from the supplied [`value`](isnotnumber.md#value-type).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isnotnumber.md#value-type) is not a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type and not an instance of [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number).

## Example usage

```typescript
// Example usage.
import { isNotNumber } from '@angular-package/type';

const anyNumber: any = 'any number';
const firstName = 'firstName';
const age = 27;
const objectNumber = new Number(927);

isNotNumber(anyNumber); // return type is `value is any`
isNotNumber(firstName); // return type is `value is string`
isNotNumber(age); // return type is `value is never`
isNotNumber(objectNumber); // return type is `value is never`// Example usage.
import { isNotNull } from '@angular-package/type';

const anyNull: any = null;
const firstName = null;

isNotNull(anyNull); // return type is `value is any`
isNotNull(firstName); // return type is `value is never`
```

