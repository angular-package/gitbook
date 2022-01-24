# every()

## `areBoolean().every()`

Checks whether **every** of the provided [`values`](./#...values-any) of [`areBoolean()`](./) is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean).

{% hint style="info" %}
The method uses [`every()`](../aredeterminer/every.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`values`](./#...values-any) of [`areBoolean()`](./) are a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean).

### Example usage

```typescript
// Example usage.
import { areBoolean } from '@angular-package/type';

areBoolean(1, true, null, new Boolean(3)).every((result, value, payload) => {
  result // false
  value // [1, true, null, Boolean]
  payload // undefined
  return result;
}); // false, boolean
```
