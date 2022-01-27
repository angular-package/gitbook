# forEach()

## `areFalse().forEach()`

The `forEach()` method executes a provided [`callback`](../aredeterminer/foreach.md#foreachcallback-foreachcallback-less-than-any-payload-greater-than) function **once** for each element of the supplied [`values`](./#...values-any) of [`areFalse()`](./).

{% hint style="info" %}
The method uses [`forEach()`](../aredeterminer/foreach.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

## Example usage

```typescript
// Example usage.
import { areFalse } from '@angular-package/type';

areFalse(true, null, false, new Boolean(false)).forEach(
  (result, value, index, array, payload) => {
    result // false, false, true, true
    value // true, null, false, Boolean
    index // 0, 1, 2, 3
    array // [ true, null, false, Boolean ]
    payload // { age: 2 }
  },
  { age: 2 }
);
```
