# every()

## `areBigInt().every()`

Checks whether **every** provided [`value`](./#...values-any) of [`areBigInt()`](./) is a [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt) type.

{% hint style="info" %}
The method uses [`every()`](../aredeterminer/every.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`values`](../aredeterminer/#...values-any) of [`areBigInt()`](./) are a [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt) type.

## Example usage

```typescript
// Example usage.
import { areBigInt } from '@angular-package/type';

areBigInt(1n, 22n).every((result, value, payload) => {
  result // true
  value /// [1n, 22n]
  payload // undefined
  return result;
}); // true, boolean
```
