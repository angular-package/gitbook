# isBoolean()

## `isBoolean()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type, or the obtained type from its [`object` class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/toString#using\_tostring\_to\_detect\_object\_class) equal to `'boolean'`, or an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) type and an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) that is equal to `true` or `false`.

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

#### <mark style="color:green;">**`Type`**</mark>**`extends`**<mark style="color:green;">**`AnyBoolean`**</mark>**`=`**<mark style="color:green;">**`boolean`**</mark>

The `Type` generic type variable constrained by generic type [`AnyBoolean`](../types/anyboolean.md) by default of [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) indicates the type of the given [`value`](isboolean.md#value-any) via the [return type](isboolean.md#return-type).

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isboolean.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isboolean.md#payload-payload) optional parameter of the [`isBoolean()`](isboolean.md#isboolean) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isboolean.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isboolean.md#payloadextendsobject-object) with optional properties from the provided [`payload`](isboolean.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isboolean.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isboolean.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Type`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement, indicating the [`value`](isboolean.md#value-any) is a generic type variable [`Type`](isboolean.md#typeextendsanyboolean-boolean) constrained by [`AnyBoolean`](../types/anyboolean.md) by default equal to the [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isboolean.md#value-any) is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean).

## Example usage

### Basic example

```typescript
// Basic example usage.
import { isBoolean } from '@angular-package/type';

isBoolean(false); // Returns `true` as `value is boolean`
isBoolean(new Boolean(false)); // Returns `true` as `value is boolean`
```

### Callback and payload parameters

```typescript
// Callback and payload parameters example usage.
import { isBoolean } from '@angular-package/type';

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
```

### String as boolean

```typescript
// String as boolean example usage.
import { isBoolean } from '@angular-package/type';

const fakeBoolean = new String('');

Object.assign(fakeBoolean, {
  get [Symbol.toStringTag](): string {
    return 'boolean';
  },
});

isBoolean(fakeBoolean); // false
typeOf(fakeBoolean); // "boolean"
typeof fakeBoolean; // "object"
```

### Boolean as string

```typescript
// Boolean as string example.
import { isBoolean } from '@angular-package/type';

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
