# forEach()

## `areNumber().forEach()`

The `forEach()` method executes a provided [`callback`](../aredeterminer/foreach.md#foreachcallback-foreachcallback-less-than-any-payload-greater-than) function **once** for each element of the supplied [`values`](./#...values-any) of [`areNumber()`](./).

{% hint style="info" %}
The method uses [`forEach()`](../aredeterminer/foreach.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Example usage

```typescript
// Example usage.
import { areNumber } from '@angular-package/type';

areNumber(1, new Number(2), Number(3), '4').forEach(
  (result, value, index, array, payload) => {
    result // true, true, true, false
    value // 1, Number, 3, '4'
    index // 0, 1, 2, 3
    array // [ 1, Number, 3, '4' ]
    payload // { age: 2 }
  },
  { age: 2 }
);
```
