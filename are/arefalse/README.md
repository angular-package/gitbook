# ★ areFalse()

## `areFalse()`

Checks if the values are a `boolean` type or an instance of `Boolean` equal to `false` by using `every()`, `forEach()` and `some()`methods of the returned object.false

{% code title="are-false.func.ts" %}
```typescript
const areFalse = <CommonPayload extends object>(...values: any[]) =>
  areDeterminer<CommonPayload>(isFalse, ...values);
```
{% endcode %}

| Generic type variables                                                                                                                                                                                                                                                                                                                                                            |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><mark style="color:green;"><strong><code>CommonPayload</code></strong></mark><strong><code>extends</code></strong><mark style="color:green;"><strong><code>object</code></strong></mark><br>The <code>CommonPayload</code> generic type variable constrained by the <code>object</code> constrains the generic type variable <code>Payload</code> of each returned method.</p> |

### Parameters

| Name: type         | Description                                                                                                                 |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| `...values: any[]` | A rest parameter of `any` type to check its elements against a `boolean` type or an instance of `Boolean` equal to `false`. |

### Returns

The **return value** is an `object` with `every()`, `some()` and `forEach()` as methods of checking supplied `values`.

### Example usage

```typescript
// Example usage.
import { areFalse } from '@angular-package/type';


```

