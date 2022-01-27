# forEach()

## `areDefined().forEach()`

The `forEach()` method executes a provided [`callback`](../aredeterminer/foreach.md#foreachcallback-foreachcallback-less-than-any-payload-greater-than) function **once** for each element of the supplied [`values`](./#...values-any) of [`areDefined()`](./).

{% hint style="info" %}
The method uses [`forEach()`](../aredeterminer/foreach.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

## Example usage

```typescript
// Example usage.
import { areDefined } from '@angular-package/type';

let age;

areDefined('1', 2, null, undefined, age).forEach(
  (result, value, index, array, payload) => {
    result // true, true, true, false, false
    value // '1', 2, null, undefined, undefined
    index // 0, 1, 2, 3, 4
    array // [ '1', 2, null, undefined, undefined ]
    payload // { age: 2 }
  },
  { age: 2 }
);
```
