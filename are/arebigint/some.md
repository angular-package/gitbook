# some()

## `areBigInt().some()`

Checks whether **some** provided [`values`](./#...values-any) of [`areBigInt()`](./) are a [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt) type.

{% hint style="info" %}
The method uses [`some()`](../aredeterminer/some.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether **some** of the provided [`values`](./#...values-any) of [`areBigInt()`](./) are a [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt) type.

## Example usage

```typescript
// Example usage.
import { areBigInt } from '@angular-package/type';

areBigInt(1n, 2, '3').some((result, value, payload) => {
  result // true
  value // [1n, 2, '3']
  payload // undefined
  return result;
});
```
