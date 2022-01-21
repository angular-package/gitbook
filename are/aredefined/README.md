# areDefined()

### `areDefined()`

Checks whether the values are `Date` by using `every()`, `forEach()` and `some()` methods of the returned object.

Checks if every of the provided `values` of `areDefined()` is defined.

{% code title="are-date.func.ts" %}
```typescript
const areDate = <CommonPayload extends object>(...values: any[]) =>
  areDeterminer<CommonPayload>(isDate, ...values);
```
{% endcode %}

| Generic type variables                                                                                                                                                                                                                                                                                                                                                            |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><mark style="color:green;"><strong><code>CommonPayload</code></strong></mark><strong><code>extends</code></strong><mark style="color:green;"><strong><code>object</code></strong></mark><br>The <code>CommonPayload</code> generic type variable constrained by the <code>object</code> constrains the generic type variable <code>Payload</code> of each returned method.</p> |

### Parameters

| Name: type         | Description                                                                                                                                                    |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `...values: any[]` | A rest parameter of `any` type to check its elements against [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Date). |

### Returns

The **return value** is an `object` with [`every()`](https://app.gitbook.com/s/HmRqpb9wXbHlBaTRCXZm/c/zkFcxLE4HTwIcknJCu1A/are/areboolean/every), [`some()`](https://app.gitbook.com/s/HmRqpb9wXbHlBaTRCXZm/c/zkFcxLE4HTwIcknJCu1A/are/areboolean/some) and [`forEach()`](https://app.gitbook.com/s/HmRqpb9wXbHlBaTRCXZm/c/zkFcxLE4HTwIcknJCu1A/are/areboolean/foreach) as methods of checking supplied `values`.

### Example usage

```typescript
// Example usage.
import { areBigInt } from '@angular-package/type';


```

