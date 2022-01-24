# every()

## `areNull().every()`

Checks whether **every** provided value of [`areNull()`](./) is [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/null).

{% hint style="info" %}
The method uses [`every()`](../aredeterminer/every.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`values`](./#...values-any) of [`areNull()`](./) are [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/null).

### Example usage

```typescript
// Example usage.
import { areNull } from '@angular-package/type';

areNull(null, undefined, false, !!null).every((result, value, payload) => {
  result // false
  value // [ null, undefined, false, false ]
  payload // undefined
  return result;
}); // false, boolean
```
