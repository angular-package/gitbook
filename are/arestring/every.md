# every()

## `areString().every()`

Checks whether **every** of the provided [`values`](./#...values-any) of [`areString()`](./) is a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String).

{% hint style="info" %}
The method uses [`every()`](../aredeterminer/every.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided values of [`areString()`](./) are a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type or an instance of [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String).

### Example usage

```typescript
// Example usage.
import { areString } from '@angular-package/type';

areString(1, '2', '3').every((result, value, payload) => {
  result // true
  value // [1, '2', '3']
  payload // undefined
  return result;
}); // false, boolean
```
