# isBooleanObject()

### `isBooleanObject()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is of the type obtained from its `Object.prototype` equal to `'boolean'` or an `object` type, and an instance of `Boolean` that is equal to `true` or `false`.

{% code title="is-boolean-object.func.ts" %}
```typescript
const isArray = <Type = any, Payload extends object = object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Array<Type> =>
  callback(
    (typeOf(value) === 'array' || typeof value === 'object') &&
      Array.isArray(value),
    value,
    payload
  );
```
{% endcode %}

| Generic type variables                                                                                                                                                                                                                                                                             |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><mark style="color:green;"><strong><code>Type</code></strong></mark><strong><code>=</code></strong><mark style="color:green;"><strong><code>any</code></strong></mark><br></p>                                                                                                                  |
| <p><mark style="color:green;"><strong><code>Payload</code></strong></mark><strong><code>extends</code></strong><mark style="color:green;"><strong><code>object</code></strong></mark><strong><code>=</code></strong><mark style="color:green;"><strong><code>object</code></strong></mark><br></p> |

### Parameters

| Name: type                               | Description                                                                                                                                                                                                                                                                                                                                                     |
| ---------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `value: any`                             | The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.                                                                                                                                                                                                                                                     |
| `callback: ResultCallback<any, Payload>` | A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function. |
| `payload?: Payload`                      | Optional `object` of generic type variable `Payload` is assigned to the `payload` of the supplied `callback` function.                                                                                                                                                                                                                                          |

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided `value` is an instance of [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean).

### Example usage

```typescript
// Example usage
import { isBooleanObject } from '@angular-package/type';

```

