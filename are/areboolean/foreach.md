# forEach()

## `areBoolean().forEach()`

The `forEach()` method executes a provided [`callback`](../aredeterminer/foreach.md#foreachcallback-foreachcallback-less-than-any-payload-greater-than) function **once** for each element of the supplied [`values`](./#...values-any) of [`areBoolean()`](./).

{% hint style="info" %}
The method uses [`forEach()`](../aredeterminer/foreach.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

## Example usage

```typescript
// Example usage.
import { areBoolean } from '@angular-package/type';

areBoolean(1, true, null, new Boolean(3)).forEach(
  (result, value, index, array, payload) => {
    result // false, true, false, true
    value // 1, true, null, Boolean
    index // 0, 1, 2, 3
    array // [ 1, true, null, Boolean ]
    payload // { age: 2 }
  },
  { age: 2 }
);
```
