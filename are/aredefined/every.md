# every()

## `areDefined().every()`

Checks whether **every** of the provided [`values`](./#...values-any) of [`areDefined()`](./) is **defined**.

{% hint style="info" %}
The method uses [`every()`](../aredeterminer/every.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`values`](./#...values-any) of [`areDefined()`](./) are **defined**.

### Example usage

```typescript
// Example usage.
import { areDefined } from '@angular-package/type';

let age;

areDefined('1', 2, null, undefined, age).every((result, value, payload) => {
  result // false
  value // [ '1', 2, null, undefined, undefined ]
  payload // undefined
  return result;
}); // false, boolean
```
