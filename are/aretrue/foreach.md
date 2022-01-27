# forEach()

## `areTrue().forEach()`

The `forEach()` method executes a provided [`callback`](../aredeterminer/foreach.md#foreachcallback-foreachcallback-less-than-any-payload-greater-than) function **once** for each element of the supplied [`values`](./#...values-any) of [`areTrue()`](./).

{% hint style="info" %}
The method uses [`forEach()`](../aredeterminer/foreach.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

## Example usage

```typescript
// Example usage.
import { areTrue } from '@angular-package/type';

const deleteElements = [true, false, false,  new Boolean(false)];

areTrue(...deleteElements).forEach(
  (result, value, index, array, payload) => {
    result // true, false, false, false
    value // true, false, false, Boolean
    index // 0, 1, 2, 3
    array // [ true, false, false, Boolean ]
    payload //  { "age": 2 }

    if (result === true) {
      // if undefined do something.
    }
  },
  { age: 2 }
);
```
