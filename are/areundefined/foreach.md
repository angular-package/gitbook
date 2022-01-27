# forEach()

## `areUndefined().forEach()`

The `forEach()` method executes a provided [`callback`](../aredeterminer/foreach.md#foreachcallback-foreachcallback-less-than-any-payload-greater-than) function **once** for each element of the supplied [`values`](./#...values-any) of [`areUndefined()`](./).

{% hint style="info" %}
The method uses [`forEach()`](../aredeterminer/foreach.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

## Example usage

```typescript
// Example usage.
import { areUndefined } from '@angular-package/type';

areUndefined(undefined, 1, 2, '3').forEach(
  (result, value, index, array, payload) => {
    result // true, false, false, false
    value // undefined, 1, 2, '3'
    index // 0, 1, 2, 3
    payload //  { age: 2 }
    array // [ undefined, 1, 2, '3' ]

    if (result === true) {
      // if undefined do something.
    }
  },
  { age: 2 }
);
```
