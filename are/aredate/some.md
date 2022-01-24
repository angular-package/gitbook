# some()

## `areDate().some()`

Checks whether **some** of the provided [`values`](./#...values-any) of [`areDate()`](./) are [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Date).

{% hint style="info" %}
The method uses [`some()`](../aredeterminer/some.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether **some** of the provided [`values`](./#...values-any) of [`areDate()`](./) are [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Date).

### Example usage

```typescript
// Example usage.
import { areDate } from '@angular-package/type';

areDate(new Date(), new Date('invalid date')).some((result, value, payload) => {
  result // true
  value // [Sat Sep 11 2021 21:37:43 GMT+0200 (Central European Summer Time), Invalid Date]
  payload // undefined
  return result;
}); // true, boolean
```
