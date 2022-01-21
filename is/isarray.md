# isArray()

### `isArray()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is the type obtained from its `Object.prototype` equal to `'array'` or an `object` type. The value is also checked by the `isArray()` method of `Array`.

{% code title="is-array.func.ts" %}
```typescript
const isArray = <Type = any, Payload extends object = object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Array<Type> =>
  callback(
    (typeOf(value) === 'array' || typeof value === 'object') &&
      Array.isArray(value),
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`=`**<mark style="color:green;">**`any`**</mark>

The `Type` generic type variable indicates the array type of the given `value` via the return type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by object indicates the type of the `payload` parameter of the main function from which it gets its value and callback function `payload` parameter.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

Optional `object` of generic type variable `Payload` is assigned to the `payload` of the supplied `callback` function.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided `value` is an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array).

### Example usage

```typescript
// Example usage
import { isArray } from '@angular-package/type';

```

