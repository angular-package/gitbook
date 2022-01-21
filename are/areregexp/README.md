# areRegExp()

### `areRegExp()`

Checks if the values are regular expressions of `RegExp` by using `every()`, `forEach()` and `some()` methods of the returned object.

{% code title="are-regexp.func.ts" %}
```typescript
const areRegExp = <CommonPayload extends object>(...values: any[]) =>
  areDeterminer<CommonPayload>(isRegExp, ...values);
```
{% endcode %}

| Generic type variables                                                                                                                                                                                                                                                                                                                                                            |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><mark style="color:green;"><strong><code>CommonPayload</code></strong></mark><strong><code>extends</code></strong><mark style="color:green;"><strong><code>object</code></strong></mark><br>The <code>CommonPayload</code> generic type variable constrained by the <code>object</code> constrains the generic type variable <code>Payload</code> of each returned method.</p> |

### Parameters

| Name: type         | Description                                                                                      |
| ------------------ | ------------------------------------------------------------------------------------------------ |
| `...values: any[]` | A rest parameter of `any` type to check its elements against the regular expression of `RegExp`. |

### Returns

The **return value** is an `object` with `every()`, `some()` and `forEach()` as methods of checking supplied `values`.

### Example usage

```typescript
// Example usage.
import { areRegExp } from '@angular-package/type';


```



