# isBoolean()

### `isBoolean()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type, or the obtained type from its `Object.prototype` equal to `'boolean'`, or an `object` type and an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) that is equal to `true` or `false`.

{% code title="is-boolean.func.ts" %}
```typescript
const isBoolean = <
  Type extends AnyBoolean = boolean,
  Payload extends object = object
>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Type =>
  callback(
    (typeof value === 'boolean' ||
    typeOf(value) === 'boolean' ||
    (typeof value === 'object' && value instanceof Boolean)) &&
    (value.valueOf() === true || value.valueOf() === false),
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`anyBoolean`**</mark>**`=`**<mark style="color:green;">**`boolean`**</mark>

The `Type` generic type variable constrained by generic type [`AnyBoolean`](../types/anyboolean.md) by default of [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) indicates the given `value` type via the return type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by object indicates the type of the `payload` parameter of the main function from which it gets its value and callback function `payload` parameter.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

Optional `object` of generic type variable `Payload` is assigned to the `payload` of the supplied `callback` function.

### Return type

#### `value is Type`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement, indicating the `value` is a generic type variable [`Type`](isboolean.md#typeextendsanyboolean-boolean) constrained by [`AnyBoolean`](../types/anyboolean.md) by default equal to the [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided `value` is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean).

### Example usage

```typescript
// Example usage.
import { isBoolean } from '@angular-package/type';

isBoolean(false); // Returns `true` as `value is boolean`
isBoolean(new Boolean(false)); // Returns `true` as `value is boolean`
isBoolean('my name', (result, value, payload) => {
  if (result === false) {
    value // "my name"
    if (payload) {
      // Change the result from `false` to `true`.
      if (payload === payload.accepted) {
        result = true;
      }
    }
  }
  return result;
}, { accepted: 'my name' }); // Returns `true` as `value is boolean`.

// Fake boolean example.
const fakeBoolean = new String('');

Object.assign(fakeBoolean, {
  get [Symbol.toStringTag](): string {
    return 'boolean';
  },
});

isBoolean(fakeBoolean); // false
typeOf(fakeBoolean); // "boolean"
typeof fakeBoolean; // "object"

// Boolean as string example.
const stringAsBoolean = new Boolean('');

Object.assign(stringAsBoolean, {
  get [Symbol.toStringTag](): string {
    return 'string';
  },
});

isBoolean(stringAsBoolean); // true
typeOf(stringAsBoolean); // "string"
typeof stringAsBoolean; // "object"
```
