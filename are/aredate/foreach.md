# forEach()

## `areDate().forEach()`

The `forEach()` method executes a provided callback function once for each element of the supplied [`values`](./#...values-any) of [`areDate()`](./).

{% hint style="info" %}
The method uses [`forEach()`](../aredeterminer/foreach.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Example usage

```typescript
// Example usage.
import { areDate } from '@angular-package/type';

areDate(new Date(), new Date('invalid date')).forEach(
  (result, value, index, array, payload) => {
    result // true, false
    value // Sat Sep 11 2021 21:38:19 GMT+0200 (Central European Summer Time, Invalid Date
    index // 0, 1
    array // [ Sat Sep 11 2021 21:38:19 GMT+0200 (Central European Summer Time), Invalid Date ]
    payload // { age: 2 }
  },
  { age: 2 }
);
```
