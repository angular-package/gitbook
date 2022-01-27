# some()

## `areFalse().some()`

Checks whether **some** of the provided [`values`](./#...values-any) of [`areFalse()`](./) are a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) equal to `false`.

{% hint style="info" %}
The method uses [`some()`](../aredeterminer/some.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether some of the provided [`values`](./#...values-any) of [`areFalse()`](./) are a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) equal to `false`.

## Example usage

```typescript
// Example usage.
import { areFalse } from '@angular-package/type';

areFalse(true, null, false, new Boolean(false)).some((result, value, payload) => {
  result // true
  value // [ true, null, false, Boolean ]
  payload // undefined
  return result;
}); // true, boolean
```
