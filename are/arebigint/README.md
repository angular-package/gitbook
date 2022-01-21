# areBigInt()

### `areBigInt()`

Checks if the values are a [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt) type by using [`every()`](every.md), [`forEach()`](foreach.md) and [`some()`](some.md) methods of the returned object.

{% code title="are-bigint.func.ts" %}
```typescript
const areBigInt = <CommonPayload extends object>(...values: any[]) =>
  areDeterminer<CommonPayload>(isBigInt, ...values);
```
{% endcode %}

| Generic type variables                                                                                                                                                                                                                                                                                                                                                            |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><mark style="color:green;"><strong><code>CommonPayload</code></strong></mark><strong><code>extends</code></strong><mark style="color:green;"><strong><code>object</code></strong></mark><br>The <code>CommonPayload</code> generic type variable constrained by the <code>object</code> constrains the generic type variable <code>Payload</code> of each returned method.</p> |

### Parameters

| Name: type         | Description                                                                                                                                                               |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `...values: any[]` | A rest parameter of `any` type to check its elements against a [`bigint`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt) type. |

### Returns

The **return value** is an `object` of [`every()`](every.md), [`some()`](some.md) and [`forEach()`](foreach.md) as methods of checking supplied `values`.
