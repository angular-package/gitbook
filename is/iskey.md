# isKey()

## `isKey()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is one of the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number), or [`symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol) type.

{% code title="is-key.func.ts" %}
```typescript
const isKey = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is PropertyKey =>
  callback(
    isStringType(value) || isNumberType(value) || isSymbol(value),
    value,
    payload
  );
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/is/lib/is-key.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](iskey.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](iskey.md#payload-payload) optional parameter of the [`isKey()`](iskey.md#iskey) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](iskey.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](iskey.md#payloadextendsobject) with optional properties from the provided [`payload`](iskey.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](iskey.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](iskey.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is PropertyKey`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](iskey.md#value-any) is `PropertyKey`.

### Returns

The **return value** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) indicating whether the provided [`value`](iskey.md#value-any) is a `PropertyKey`.

## Example usage

### Key of `string`

```typescript
// Example string usage.
import { isKey } from '@angular-package/type';

const STRING = 'surname';
const STRING_INSTANCE = new String(STRING);
isKey(STRING); // true
isKey(STRING_INSTANCE); // true
```

### Key of `number`

```typescript
// Example number usage.
import { isKey } from '@angular-package/type';

const NUMBER = 27;
const NUMBER_INSTANCE = new Number(NUMBER);
isKey(NUMBER); // true
isKey(NUMBER_INSTANCE); // true
```

### Key of `symbol`

```typescript
// Example symbol usage.
import { isKey } from '@angular-package/type';

const STRING = 'surname';
const NUMBER = 27;

const SYMBOL_NUMBER: unique symbol = Symbol(NUMBER);
const SYMBOL_STRING: unique symbol = Symbol(STRING);

isKey(SYMBOL_NUMBER); // true
isKey(SYMBOL_STRING); // true
```
