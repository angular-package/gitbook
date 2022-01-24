# every()

## `areSymbol().every()`

Checks if every of the provided [`values`](./#...values-any) of [`areSymbol()`](./) is a [`symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol) type.

{% hint style="info" %}
The method uses [`every()`](../aredeterminer/every.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided values of [`areSymbol()`](./) are a [`symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol) type.

### Example usage

```typescript
// Example usage.
import { areSymbol } from '@angular-package/type';

areSymbol(Symbol(1), 2, Symbol(3), 4).every((result, value, payload) => {
  result // true
  value // [ Symbol(1), 2, Symbol(3), 4 ]
  payload // undefined
  return result;
}); // false, boolean
```
