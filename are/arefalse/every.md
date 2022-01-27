# every()

## `areFalse().every()`

Checks whether **every** provided value of rest parameter [`values`](./#...values-any) of the [`areFalse()`](./) function is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) equal to false.

{% hint style="info" %}
The method uses [`every()`](../aredeterminer/every.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided values of [`areFalse()`](./) are a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) equal to `false`.

## Example usage

```typescript
// Example usage.
import { areFalse } from '@angular-package/type';

areFalse(true, null, false, new Boolean(false)).every((result, value, payload) => {
  result // false
  value // [ true, null, false, Boolean ]
  payload // undefined
  return result;
}); // false, boolean
```
