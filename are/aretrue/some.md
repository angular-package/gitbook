# some()

### `areTrue().some()`

Checks whether some of the provided [`values`](./#...values-any) of [`areTrue()`](./) are a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) equal to `true`.

{% hint style="info" %}
The method uses [`some()`](../aredeterminer/some.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether **some** of the provided [`values`](./#...values-any) of [`areTrue()`](./) are a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) equal to `true`.

### Example usage

```typescript
// Example usage.
import { areTrue } from '@angular-package/type';

const deleteElements = [true, false, false,  new Boolean(false)];

areTrue(...deleteElements).some((result, value, payload) => {
  result // true
  value // [ true, false, false, Boolean ]
  payload // undefined
  return result;
}); // true, boolean
```
