# some()

## `areNull().some()`

Checks whether **some** of the provided [`values`](./#...values-any) of [`areNull()`](./) are [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/null).

{% hint style="info" %}
The method uses [`some()`](../aredeterminer/some.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether some of the provided [`values`](./#...values-any) of [`areNull()`](./) are [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/null).

### Example usage

```typescript
// Example usage.
import { areNull } from '@angular-package/type';

areNull(true, null, false, new Boolean(false)).some((result, value, payload) => {
  result // true
  value // [ null, undefined, false, false ]
  payload // undefined
  return result;
}); // true, boolean
```
