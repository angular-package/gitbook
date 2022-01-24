# ★ areString()

## `areString()`

Checks if the values are a `string` type or an instance of `String` by using `every()`, `forEach()` and `some()` methods of the returned object.

{% code title="are-string.func.ts" %}
```typescript
const areString = <CommonPayload extends object>(...values: any[]) =>
  areDeterminer<CommonPayload>(isString, ...values);
```
{% endcode %}

| Generic type variables                                                                                                                                                                                                                                                                                                                                                            |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><mark style="color:green;"><strong><code>CommonPayload</code></strong></mark><strong><code>extends</code></strong><mark style="color:green;"><strong><code>object</code></strong></mark><br>The <code>CommonPayload</code> generic type variable constrained by the <code>object</code> constrains the generic type variable <code>Payload</code> of each returned method.</p> |

### Parameters

| Name: type         | Description                                                                                              |
| ------------------ | -------------------------------------------------------------------------------------------------------- |
| `...values: any[]` | A rest parameter of `any` type to check its elements against a `string` type or an instance of `String`. |

### Returns

The **return value** is an `object` with `every()`, `some()` and `forEach()` as methods of checking supplied `values`.

### Example usage

```typescript
// Example usage.
import { areString } from '@angular-package/type';


```

