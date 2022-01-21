# isDefined()

### `isDefined()`

Checks if any value is not an `undefined` type and is not equal to `undefined`.

{% code title="is-defined.func.ts" %}
```typescript
const isDefined = <Type, Payload extends object = object>(
  value: Type,
  callback: ResultCallback<Type, Payload> = resultCallback,
  payload?: Payload
): value is Defined<Type> =>
  callback(typeof value !== 'undefined' && value !== undefined, value, payload);
```
{% endcode %}

### Parameters

| Name: type                               | Description                                                                                                                                                                                                                                                                                                                                                     |
| ---------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `value: any`                             | The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.                                                                                                                                                                                                                                                     |
| `callback: ResultCallback<any, Payload>` | A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function. |
| `payload?: Payload`                      | Optional `object` of generic type variable `Payload` is assigned to the `payload` of the supplied `callback` function.                                                                                                                                                                                                                                          |

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided `value` is defined, not `undefined`.

### Example usage

```typescript
// Example usage
import { isDefined } from '@angular-package/type';

```

