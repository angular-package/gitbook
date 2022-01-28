# isArray()

## `isArray()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is of the type obtained from its [`object` class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/toString#using\_tostring\_to\_detect\_object\_class) equal to `'array'` or an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) type and passes the test [`Array.isArray()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/isArray) method.

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

The `Type` generic type variable indicates the [`array`](https://www.typescriptlang.org/docs/handbook/basic-types.html#array) element type, which by default is [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) of the given [`value`](isarray.md#value-any) via the [return type](isarray.md#return-type).

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isarray.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isarray.md#payload-payload) optional parameter of the [`isArray()`](isarray.md#isarray) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isarray.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isarray.md#payloadextendsobject-object) with optional properties from the provided [`payload`](isarray.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isarray.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isarray.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Array<Type>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) because of used the `is` operator indicating the value is an [`array`](https://www.typescriptlang.org/docs/handbook/basic-types.html#array) that takes generic type variable [`Type`](isarray.md#type-any) by default of value [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) as the type of its elements.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isarray.md#value-any) is an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array).

## Example usage

### Basic example

```typescript
// Basic example.
import { isArray } from '@angular-package/type'; 

const ARRAY_NUMBER = [1, 2, 3];
const ARRAY_STRING = ['a', 'b', 'c'];

isArray(ARRAY_NUMBER); // Returns `true` as `value is any[]`
isArray<string>(ARRAY_STRING); // Returns `true` as `value is string[]`
```

### Fake array

```typescript
// Fake array example.
import { isArray } from '@angular-package/type'; 

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
```

### Callback and payload parameters

```typescript
// Example usage with callback and payload.
import { isArray } from '@angular-package/type';

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
