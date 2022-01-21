# isDate()

### `isDate()`

Checks if any value is of the type obtained from its `Object.prototype` equal to `'date'` or an `object` type, and an instance of `Date`. The value is checked against a valid date by using `isNaN()` method.

{% code title="is-date.func.ts" %}
```typescript
const isDate = <Payload extends object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Date =>
  callback(
    (typeOf(value) === 'date' || typeof value === 'object') &&
    value instanceof Date === true &&
    !isNaN(value),
    value,
    payload
  );
```
{% endcode %}

| Generic type variables                                                                                                                                                                        |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><mark style="color:green;"><strong><code>Payload</code></strong></mark><strong><code>extends</code></strong><mark style="color:green;"><strong><code>object</code></strong></mark><br></p> |

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

Optional `object` of generic type variable `Payload` is assigned to the `payload` of the supplied `callback` function.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided `value` is a date.

### Example usage

```typescript
// Example usage
import { isDate } from '@angular-package/type';

```

