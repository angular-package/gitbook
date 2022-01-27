# isNotFunction()

## `isNotFunction()`

Checks if the [`value`](isnotfunction.md#value-type) is **not** the type obtained from its [object class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/toString#using\_tostring\_to\_detect\_object\_class) equal to `'function'`, **not** a [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function) type and **not** an instance of [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function).

{% code title="is-not-function.func.ts" %}
```typescript
const isNotFunction = <Type, Payload extends object = object>(
  value: Type,
  callback: ResultCallback<Type, Payload> = resultCallback,
  payload?: Payload
): value is Never<Function, Type> =>
  callback(
    typeOf(value) !== 'function' &&
    typeof value !== 'function' &&
    value instanceof Function === false,
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>

A generic type variable `Type` indicates the captured type of the given [`value`](isnotfunction.md#value-array-less-than-type-greater-than) via the [return type](isnotfunction.md#return-type) `value is Never<Function, Type>` and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](isnotfunction.md#callback-resultcallback-less-than-array-less-than-type-greater-than-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isnotfunction.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isnotfunction.md#payload-payload) optional parameter of the [`isNotFunction()`](isnotfunction.md#isnotfunction) function from which it captures its value.

### Parameters

#### `value: Type`

The `value` of generic type variable [`Type`](isnotfunction.md#type), by default of the type captured from itself to check.

#### `callback: ResultCallback<Type, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isnotfunction.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isnotfunction.md#payloadextendsobject) with optional properties from the provided [`payload`](isnotfunction.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isnotfunction.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isnotfunction.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Never<Function, Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isnotfunction.md#value-type) is a generic type [`Never`](../types/never.md) that takes a generic type variable [`Type`](isnotfunction.md#type) by default of value captured from the supplied [`value`](isnotfunction.md#value-type), but on the captured type [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function) changes to [`never`](https://www.typescriptlang.org/docs/handbook/basic-types.html#never).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isnotfunction.md#value-type) is not a [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function).

## Example usage

```typescript
// Example usage.
import { IsNotFunction } from '@angular-package/type';

const anyFunc: any = (x: number) => x + 5;
const myFunc = (x: string) => x;

isNotFunction(anyFunc); // false; return type is `value is any`
isNotFunction(myFunc); // false; return type is `value is never`
isNotFunction('maybe i am not a function'); // true; return type is `value is string`
```
