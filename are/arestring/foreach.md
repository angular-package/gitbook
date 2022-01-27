# forEach()

## `areString().forEach()`

The `forEach()` method executes a provided [`callback`](../aredeterminer/foreach.md#foreachcallback-foreachcallback-less-than-any-payload-greater-than) function **once** for each element of the supplied [`values`](./#...values-any) of [`areString()`](./).

{% hint style="info" %}
The method uses [`forEach()`](../aredeterminer/foreach.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

## Example usage

```typescript
// Example usage.
import { areString } from '@angular-package/type';

areString(1, '2', '3', false).forEach(
  (result, value, index, array, payload) => {
    result // false, true, true, false
    value // 1, '2', '3', false
    index // 0, 1, 2, 3
    array // [ 1, '2', '3', false ]
    payload // { age: 2 }
  },
  { age: 2 }
);
```
