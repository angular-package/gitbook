# some()

## `areUndefined().some()`

Checks whether **some** of the provided [`values`](./#...values-any) of [`areUndefined()`](./) are [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

{% hint style="info" %}
The method uses [`some()`](../aredeterminer/some.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether **some** of the provided [`values`](./#...values-any) of [`areUndefined()`](./) are [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

## Example usage

```typescript
// Example usage.
import { areUndefined } from '@angular-package/type';

areUndefined(undefined, 2, 3, new String('4')).some((result, value, payload) => {
  result // false
  value // [ undefined, 2, 3, String]
  payload // undefined
  return result;
}); // true, boolean
```
