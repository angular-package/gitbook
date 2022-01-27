# forEach()

## `areNull().forEach()`

The `forEach()` method executes a provided [`callback`](../aredeterminer/foreach.md#foreachcallback-foreachcallback-less-than-any-payload-greater-than) function **once** for each element of the supplied [`values`](./#...values-any) of [`areNull()`](./).

{% hint style="info" %}
The method uses [`forEach()`](../aredeterminer/foreach.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

## Example usage

```typescript
// Example usage.
import { areNull } from '@angular-package/type';

areNull(true, null, false, new Boolean(false)).forEach(
  (result, value, index, array, payload) => {
    result // false, true, false, false
    value // null, undefined, false, false
    index // 0, 1, 2, 3
    array // [ null, undefined, false, false ]
    payload // { age: 2 }
  },
  { age: 2 }
);
```
