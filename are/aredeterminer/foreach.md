# forEach()

## `areDeterminer().forEach()`

The `forEach()` method executes a provided [`callback`](foreach.md#foreachcallback-foreachcallback-less-than-any-payload-greater-than) function **once** for each element of the supplied [`values`](./#...values-any).

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

### Generic type variables

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`CommonPayload`**</mark>

The `Payload` generic type variable constrained by generic type variable [`CommonPayload`](./#commonpayloadextendsobject) indicates the type of the [`payload`](foreach.md#payload-payload) parameter from which it gets its value.

### Parameters

#### `forEachCallback: ForEachCallback<any, Payload>`

A callback `function` of [`ForEachCallback`](../../types/foreachcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, `index` of each element, the provided `values` and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](foreach.md#payloadextendscommonpayload) is assigned to the [`payload`](../../types/resultcallback.md#payload-payload) of the given [`callback`](foreach.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Example usage

```typescript
// Example usage.
import { areDeterminer } from '@angular-package/type';


```
