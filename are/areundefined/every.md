# every()

### `areUndefined().every()`

Checks whether every provided [`value`](./#...values-any) of [`areUndefined()`](./) is [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

{% hint style="info" %}
The method uses [`every()`](../aredeterminer/every.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`values`](./#...values-any) of [`areUndefined()`](./) are [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

### Example usage

```typescript
// Example usage.
import { areUndefined } from '@angular-package/type';

areUndefined(undefined, 2, 3, new String('4')).every((result, value, payload) => {
  result // false
  value // [ undefined, 2, 3, String]
  payload // undefined
  return result;
}); // false, boolean
```
