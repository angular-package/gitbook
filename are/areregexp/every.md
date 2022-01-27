# every()

## `areRegExp().every()`

Checks whether every of the provided [`values`](./#...values-any) of [`areRegExp()`](./) is a regular expression of [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/RegExp).

{% hint style="info" %}
The method uses [`every()`](../aredeterminer/every.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided values of [`areRegExp()`](./) are regular expressions of a [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/RegExp).

### Example usage

```typescript
// Example usage.
import { areRegExp } from '@angular-package/type';

areRegExp(/^[]/, /^[]/, /^[]/, 3).every((result, value, payload) => {
  result // false
  value // [/^[]/, /^[]/, /^[]/, 3]
  payload // undefined
  return result;
}); // false, boolean
```
