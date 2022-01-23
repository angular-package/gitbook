# forEach()

### `areDeterminer().forEach()`

The `forEach()` method executes a provided callback function once for each element of the supplied `values`.

{% code title="are-determiner.func.ts" %}
```typescript
{
  forEach: <Payload extends CommonPayload>(
    forEachCallback: ForEachCallback<any, Payload>,
    payload?: Payload
  ) => {
    isArray(values) &&
      isFunction(forEachCallback) &&
      values.forEach((value, index) =>
        forEachCallback(checkFn(value), value, index, values, payload)
      );
  },
}
```
{% endcode %}

| Generic type variables                                                                                                                                                                                                                                                                                                                                                                                    |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><mark style="color:green;"><strong><code>Payload</code></strong></mark><strong><code>extends</code></strong><mark style="color:green;"><strong><code>CommonPayload</code></strong></mark><br>The <code>Payload</code> generic type variable constrained by generic type variable <code>CommonPayload</code> indicates the type of the <code>payload</code> parameter from which it gets its value.</p> |

### Parameters

| Name: type                                       | Description                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `forEachCallback: ForEachCallback<any, Payload>` | A callback `function` of [`ForEachCallback`](../../type/foreachcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, `index` of each element, the provided `values` and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle. |
| `payload?: Payload`                              | Optional `object` of generic type variable `Payload` is assigned to the `payload` of the supplied `callback` function.                                                                                                                                                                                                            |

### Example usage

```typescript
// Example usage.
import { areDeterminer } from '@angular-package/type';


```
