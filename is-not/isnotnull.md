# isNotNull()

## `isNotNull()`

Checks if the [`value`](isnotnull.md#value-type) is **not** the type obtained from its [object class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/toString#using\_tostring\_to\_detect\_object\_class) equal to `'null'` and **not** equal to [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/null).

{% code title="is-not-null.func.ts" %}
```typescript
const isNotNull = <Type, Payload extends object = object>(
  value: Type,
  callback: ResultCallback<Type, Payload> = resultCallback,
  payload?: Payload
): value is Never<null, Type> =>
  callback(typeOf(value) !== 'null' && value !== null, value, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>

A generic type variable `Type` indicates the captured type of the given [`value`](isnotnull.md#value-array-less-than-type-greater-than) via the [return type](isnotnull.md#return-type) `value is Never<null, Type>` and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](isnotnull.md#callback-resultcallback-less-than-array-less-than-type-greater-than-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isnotnull.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isnotnull.md#payload-payload) optional parameter of the [`isNotNull()`](isnotnull.md#isnotfunction) function from which it captures its value.

### Parameters

#### `value: Type`

The `value` of generic type variable [`Type`](isnotnull.md#type), by default of the type captured from itself to check.

#### `callback: ResultCallback<Type, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isnotnull.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isnotnull.md#payloadextendsobject) with optional properties from the provided [`payload`](isnotnull.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isnotnull.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isnotnull.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Never<null, Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isnotnull.md#value-type) is a generic type [`Never`](../types/never.md) that takes a generic type variable [`Type`](isnotnull.md#type) by default of value captured from the supplied [`value`](isnotnull.md#value-type), but on the captured [`null`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined) changes to [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isnotnull.md#value-type) is not [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/null).&#x20;

## Example usage

```typescript
// Example usage.
import { isNotNull } from '@angular-package/type';

const anyNull: any = null;
const firstName = null;

isNotNull(anyNull); // return type is `value is any`
isNotNull(firstName); // return type is `value is never`
```

