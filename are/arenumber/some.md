# some()

## `areNumber().some()`

Checks whether **some** of the provided [`values`](./#...values-any) of [`areNumber()`](./) are a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type or an instance of [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number).

{% hint style="info" %}
The method uses [`some()`](../aredeterminer/some.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether **some** of the provided [`values`](./#...values-any) of [`areNumber()`](./) are a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type or an instance of [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number).

### Example usage

```typescript
// Example usage.
import { areNumber } from '@angular-package/type';

areNumber(1, new Number(2), Number(3), '4').some((result, value, payload) => {
  result // true
  value // [ 1, Number, 3, '4' ]
  payload // undefined
  return result;
}); // true, boolean
```
