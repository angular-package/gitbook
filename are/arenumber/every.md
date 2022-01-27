# every()

## `areNumber().every()`

Checks whether every of the provided  of [`areNumber()`](./) is a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type or an instance of [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number).

{% hint style="info" %}
The method uses [`every()`](../aredeterminer/every.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided values of [`areNumber()`](./) are a [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type or an instance of [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number).

## Example usage

```typescript
// Example usage.
import { areNumber } from '@angular-package/type';

areNumber(1, new Number(2), Number(3), '4').every((result, value, payload) => {
  result // false
  value // [ 1, Number, 3, '4' ]
  payload // undefined
  return result;
}); // false, boolean
```
