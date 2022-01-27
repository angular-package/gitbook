# every()

## `areDeterminer().every()`

Checks whether **every** of the provided [`values`](./#...values-any) pass the test implemented by the given [`checkFn`](./#checkfn-function) function.

{% code title="are-determiner.func.ts" %}
```typescript
{
  every: <Payload extends CommonPayload>(
    callback: ResultCallback<any, Payload> = resultCallback,
    payload?: Payload
  ): boolean =>
    callback(
      values.every((value) => checkFn(value)),
      values,
      payload
    ),
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`CommonPayload`**</mark>

The `Payload` generic type variable constrained by the generic type variable [`CommonPayload`](./#commonpayloadextendsobject) indicates the type of optional parameter [`payload`](../../types/resultcallback.md#payload-payload) of the supplied [`callback`](every.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](every.md#payload-payload) optional parameter of the [`areDeterminer().every()`](every.md#aredeterminer-.every) method from which it captures its value.

### Parameters

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](every.md#payloadextendscommonpayload) is assigned to the [`payload`](../../types/resultcallback.md#payload-payload) of the given [`callback`](every.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`values`](./#...values-any) passed the test implemented by the given [`checkFn`](./#checkfn-function) function.

## Example usage

```typescript
// Example usage.
import { areDeterminer } from '@angular-package/type';


```
