# some()

## `areRegExp().some()`

Checks whether **some** of the provided [`values`](./#...values-any) of [`areRegExp()`](./) are regular expressions of [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/RegExp).

{% hint style="info" %}
The method uses [`some()`](../aredeterminer/some.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether some of the provided `values` of [`areRegExp()`](./) are [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/RegExp) type.

## Example usage

```typescript
// Example usage.
import { areRegExp } from '@angular-package/type';

areRegExp(/^[]/, /^[]/, /^[]/, 3).some((result, value, payload) => {
  result // true
  value // [/^[]/, /^[]/, /^[]/, 3]
  payload // undefined
  return result;
});
```
