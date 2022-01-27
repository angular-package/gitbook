# every()

## `areDate().every()`

Checks whether **every** provided [`value`](./#...values-any) of [`areDate()`](./) is a [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Date).

{% hint style="info" %}
The method uses [`every()`](../aredeterminer/every.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`values`](./#...values-any) of [`areDate()`](./) are [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Date).

## Example usage

```typescript
// Example usage.
import { areDate } from '@angular-package/type';

areDate(new Date(), new Date('invalid date')).every((result, value, payload) => {
  result // false
  value // [Sat Sep 11 2021 21:36:43 GMT+0200 (Central European Summer Time), Invalid Date]
  payload // undefined
  return result;
}); // false, boolean
```
