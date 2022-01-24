# forEach()

## `areSymbol().forEach()`

The `forEach()` method executes a provided [`callback`](../aredeterminer/foreach.md#foreachcallback-foreachcallback-less-than-any-payload-greater-than) function **once** for each element of the supplied [`values`](./#...values-any) of [`areSymbol()`](./).

{% hint style="info" %}
The method uses [`forEach()`](../aredeterminer/foreach.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Example usage

```typescript
// Example usage.
import { areSymbol } from '@angular-package/type';

areSymbol(Symbol(1), 2, Symbol(3), 4).forEach(
  (result, value, index, array, payload) => {
    result // true, false, true, false
    value // Symbol(1), 2, Symbol(3), 4
    index // 0, 1, 2, 3
    array // [ Symbol(1), 2, Symbol(3), 4 ]
    payload //  { age: 2 }

    if (result === true) {
      // if undefined do something.
    }
  },
  { age: 2 }
); // void
```
