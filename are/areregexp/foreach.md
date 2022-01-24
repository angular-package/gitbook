# forEach()

## `areRegExp().forEach()`

The `forEach()` method executes a provided [`callback`](../aredeterminer/foreach.md#foreachcallback-foreachcallback-less-than-any-payload-greater-than) function **once** for each element of the supplied [`values`](./#...values-any) of [`areRegExp()`](./).

{% hint style="info" %}
The method uses [`forEach()`](../aredeterminer/foreach.md) method of [`areDeterminer()`](../aredeterminer/).
{% endhint %}

### Example usage

```typescript
// Example usage.
import { areRegExp } from '@angular-package/type';

areRegExp(/^[]/, /^[]/, /^[]/, 3).forEach(
  (result, value, index, payload, array) => {
    result // true, true, true, false
    value // /^[]/, /^[]/, /^[]/, 4
    index // 0, 1, 2, 3
    array // [ /^[]/, /^[]/, /^[]/, 3 ]
    payload // { age: 2 }
    if (result === true) {
      // Do something.
    }
    return result;
  },
  { age: 2 }
);
```
