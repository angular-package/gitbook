# some()

## `areSymbol().some()`

Checks whether **some** of the provided [`values`](./#...values-any) of [`areSymbol()`](./) are a [`symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol) type.

{% hint style="info" %}
The method uses [`some()`](../aredeterminer/some.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether **some** of the provided [`values`](./#...values-any) of [`areSymbol()`](./) are a [`symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol) type.

## Example usage

```typescript
// Example usage.
import { areSymbol } from '@angular-package/type';

areSymbol(Symbol(1), 2, Symbol(3), 4).some((result, value, payload) => {
  result // true
  value // [ Symbol(1), 2, Symbol(3), 4 ]
  payload // undefined
  return result;
}); // true, boolean
```
