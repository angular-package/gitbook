# areNumber()

### `areFalse()`

Checks if the values are `null` by using `every()`, `forEach()` and `some()` methods of the returned object.

{% code title="are-number.func.ts" %}
```typescript
const areNumber = <CommonPayload extends object>(...values: any[]) =>
  areDeterminer<CommonPayload>(isNumber, ...values);
```
{% endcode %}

| Generic type variables                                                                                                                                                                                                                                                                                                                                                            |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><mark style="color:green;"><strong><code>CommonPayload</code></strong></mark><strong><code>extends</code></strong><mark style="color:green;"><strong><code>object</code></strong></mark><br>The <code>CommonPayload</code> generic type variable constrained by the <code>object</code> constrains the generic type variable <code>Payload</code> of each returned method.</p> |

### Parameters

| Name: type         | Description                                                                                              |
| ------------------ | -------------------------------------------------------------------------------------------------------- |
| `...values: any[]` | A rest parameter of `any` type to check its elements against a `number` type or an instance of `Number`. |

### Returns

The **return value** is an `object` with `every()`, `some()` and `forEach()` as methods of checking supplied `values`.

### Example usage

```typescript
// Example usage.
import { areNumber } from '@angular-package/type';


```

