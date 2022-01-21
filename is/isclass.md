# isClass()

### `isClass()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is a `function` type or of the type obtained from its `Object.prototype` equal to `'function'` and an instance of `Function`. It also confirms it's a `class` by using `regexp` on the obtained string from its `Function.prototype`.

{% code title="is-class.func.ts" %}
```typescript
const isClass = <Class = Function, Payload extends object = object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Class =>
  callback(
    typeof value === 'function' ||
    (typeOf(value) === 'function' && value instanceof Function)
    ? /class/.test(Function.prototype.toString.call(value).slice(0, 5))
    : false,
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Class`**</mark>**`=`**<mark style="color:green;">**`Function`**</mark>

Class

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

Payload

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

Optional `object` of generic type variable `Payload` is assigned to the `payload` of the supplied `callback` function.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided `value` is a `class`.

### Example usage

```typescript
// Example usage
import { isClass } from '@angular-package/type';

```

