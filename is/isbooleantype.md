# isBooleanType()

## `isBooleanType()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is a [`boolean`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type equal to `true` or `false`.

{% code title="is-boolean-type.func.ts" %}
```typescript
const isBooleanType = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is boolean =>
  callback(
    typeof value === 'boolean' && (value === true || value === false),
    value,
    payload
  );
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isbooleantype.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isbooleantype.md#payload-payload) optional parameter of the [`isBooleanType()`](isbooleantype.md#isbooleantype) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](isbooleantype.md#payloadextendsobject) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isbooleantype.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isbooleantype.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is boolean`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isbooleantype.md#value-any) is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type.

### Example usage

```typescript
// Example usage.
import { isBooleanType } from '@angular-package/type';

isBooleanType(false); // true
isBooleanType(new Boolean(false)); // false
```
