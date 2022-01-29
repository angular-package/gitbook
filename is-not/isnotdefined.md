# isNotDefined()

## `isNotDefined()`

Checks if the [`value`](isnotdefined.md#value-type) is not the type obtained from its [object class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/toString#using\_tostring\_to\_detect\_object\_class) equal to `'undefined'`, not an [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined) type and is not equal to [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

{% code title="is-not-defined.func.ts" %}
```typescript
const isNotDefined = <Type, Payload extends object = object>(
  value: Type,
  callback: ResultCallback<Type, Payload> = resultCallback,
  payload?: Payload
): value is Undefined<Type> =>
  callback(
    typeOf(value) === 'undefined' &&
      typeof value === 'undefined' &&
      value === undefined,
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>

A generic type variable `Type` indicates the captured type of the given [`value`](isnotdefined.md#value-type) via the [return type](isnotdefined.md#return-type) `value is Undefined<Type>` and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](isnotdefined.md#callback-resultcallback-less-than-array-less-than-type-greater-than-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isnotdefined.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](isnotdefined.md#payload-payload) optional parameter of the [`isNotDefined()`](isnotdefined.md#isnotboolean) function from which it captures its value.

### Parameters

#### `value: Type`

The `value` of generic type variable [`Type`](isnotdefined.md#type), by default of the type captured from itself to check.

#### `callback: ResultCallback<Type, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isnotdefined.md#value-type) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isnotdefined.md#payloadextendsobject-object) with optional properties from the provided [`payload`](isnotdefined.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isnotdefined.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isnotdefined.md#callback-resultcallback-less-than-type-payload-greater-than) function.

### Return type

#### `value is Undefined<Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isnotdefined.md#value-type) is a generic type [`Undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) that takes a generic type variable [`Type`](isnotdefined.md#type) by default of value captured from the supplied [`value`](isnotdefined.md#value-type) which changes to [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never) on the captured type [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](isnotdefined.md#value-type) is not defined, is [`undefined`](https://developer.mozilla.org/en-US/docs/Glossary/undefined).

## Example usage

```typescript
// Example usage.
import { isNotDefined } from '@angular-package/type';

const anyUndefined: any = undefined;
const firstName = undefined;
const surname = 'My last name ';

isNotDefined(anyUndefined); // true; return type is `value is any`
isNotDefined(firstName); // true;  return type is `value is undefined`
isNotDefined(surname); // false; return type is `value is never`
```
