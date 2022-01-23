# some()

### `areDeterminer().some()`

Checks if some of the provided `values` pass the test implemented by the given `checkFn`.

{% code title="are-determiner.func.ts" %}
```typescript
{
  some: <Payload extends CommonPayload>(
    callback: ResultCallback<any, Payload> = resultCallback,
    payload?: Payload
  ): boolean =>
    callback(
      isArray(values) ? values.some((value) => checkFn(value)) : false,
      values,
      payload
    ),
}
```
{% endcode %}

| Generic type variables                                                                                                                                                                                                                                                                                                                                                                                    |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><mark style="color:green;"><strong><code>Payload</code></strong></mark><strong><code>extends</code></strong><mark style="color:green;"><strong><code>CommonPayload</code></strong></mark><br>The <code>Payload</code> generic type variable constrained by generic type variable <code>CommonPayload</code> indicates the type of the <code>payload</code> parameter from which it gets its value.</p> |

### Parameters

| Name: type                               | Description                                                                                                                                                                                                                                                                                                                                                       |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `callback: ResultCallback<any, Payload>` | A callback `function` of [`ResultCallback`](../../type/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function. |
| `payload?: Payload`                      | Optional `object` of generic type variable `Payload` is assigned to the `payload` of the supplied `callback` function.                                                                                                                                                                                                                                            |

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether some of the provided `values` passed the test of the given `checkFn`.

### Example usage

```typescript
// Example usage.
import { areDeterminer } from '@angular-package/type';

```
