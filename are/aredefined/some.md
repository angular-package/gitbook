# some()

## `areDefined().some()`

Checks whether some of the provided [`values`](./#...values-any) of [`areDefined()`](./) are defined.

{% hint style="info" %}
The method uses [`some()`](../aredeterminer/some.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether **some** of the provided [`values`](./#...values-any) of [`areDefined()`](./) are **defined**.

## Example usage

```typescript
// Example usage.
import { areDefined } from '@angular-package/type';

let age;

areDefined('1', 2, null, undefined, age).some((result, value, payload) => {
  result // true
  value // [ '1', 2, null, undefined, undefined ]
  payload // undefined
  return result;
}); // true, boolea

```
