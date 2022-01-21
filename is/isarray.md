# isArray()

### `isArray()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is the type obtained from its `Object.prototype` equal to `'array'` or an `object` type. The value is also checked by the [`isArray()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/isArray) method of `Array`.

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

The `Type` generic type variable indicates the [`array`](https://www.typescriptlang.org/docs/handbook/basic-types.html#array) element type, which by default is [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) of the given `value` via the return type.

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

#### `value is Array<Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) because of used the `is` operator indicating the value is an [`array`](https://www.typescriptlang.org/docs/handbook/basic-types.html#array) that takes generic type variable [`Type`](isarray.md#type-any) by default of value [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) as the type of its elements.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided `value` is an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array).

### Example usage

```typescript
// Example usage.
import { isArray } from '@angular-package/type'; 

const ARRAY_NUMBER = [1, 2, 3];
const ARRAY_STRING = ['a', 'b', 'c'];

isArray(ARRAY_NUMBER); // Returns `true` as `value is any[]`
isArray<string>(ARRAY_STRING); // Returns `true` as `value is string[]`

// Fake array example.
const fakeArray = new String('');

Object.assign(fakeArray, {
  get [Symbol.toStringTag](): string {
    return 'array';
  }
});

isArray(fakeArray), // false
typeOf(fakeArray), // "array"
typeof fakeArray, // "object"
Array.isArray(fakeArray) // false

// Example usage with callback and payload.
isArray([1, 2, 3], (result, value, payload) => {
  if (result === true) {
    // Returns `(3) [1, 2, 3]`
    value

    if (payload) {
      // Returns `{ "1": "First", "2": "Second", "3": "Third" }`
      payload.transform;
    }
  }
  return result;
}, { transform: { 1: 'First', 2: 'Second', 3: 'Third'} }); // Returns `true` as `value is any[]`
```
