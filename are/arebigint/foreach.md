# forEach()

## `areBigInt().forEach()`

The `forEach()` method executes a provided [`callback`](../aredeterminer/foreach.md#foreachcallback-foreachcallback-less-than-any-payload-greater-than) function **once** for each element of the supplied [`values`](./#...values-any) of [`areBigInt()`](./).&#x20;

{% hint style="info" %}
The method uses [`forEach()`](../aredeterminer/foreach.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Example usage

```typescript
// Example usage.
import { areBigInt } from '@angular-package/type';

areBigInt(1n, 2, '3').forEach(
  (result, value, index, array, payload) => {
    result // true, false, false
    value // 1n, 2, 3
    index // 0, 1, 2
    array // [ 1n, 2, 3 ]
    payload // undefined
    return result;
  },
  { age: 2 }
);
```
