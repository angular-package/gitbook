# some()

## `areBoolean().some()`

Checks whether some of the provided [`values`](./#...values-any) of [`areBoolean()`](./) are a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) type or an instance of [`Boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean).

{% hint style="info" %}
The method uses [`some()`](../aredeterminer/some.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether **some** of the provided [`values`](./#...values-any) of [`areBoolean()`](./) are a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type or an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean).

## Example usage

```typescript
// Example usage.
import { areBoolean } from '@angular-package/type';

areBoolean(1, true, null, new Boolean(3)).some((result, value, payload) => {
  result // true
  value // [1, true, null, Boolean]
  payload // undefined
  return result;
}); // true, boolean
```
