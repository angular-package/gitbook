# ResultCallback

### `ResultCallback<Value, Payload>`

Represents a callback function with parameters, the [`value`](resultcallback.md#value-value) that has been checked, the [`result`](resultcallback.md#result-boolean) of this check, and an optional [`payload`](resultcallback.md#payload-payload).

{% code title="result-callback.type.ts" %}
```typescript
type ResultCallback<Value = any, Payload = object> = (
  result: boolean,
  value: Value,
  payload?: Payload
) => boolean;
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`=`<mark style="color:green;">`any`</mark>

Generic type variable `Value` indicates the type of the function [`value`](resultcallback.md#value-value) parameter and by default it's set to [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any).

#### <mark style="color:green;">`Payload`</mark>`=`<mark style="color:green;">`object`</mark>

Generic type variable `Payload` indicates the type of the function [`payload`](resultcallback.md#payload-payload) parameter, and by default it's set to [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object).

### Parameters

#### `result: boolean`

The check result of the given [`value`](resultcallback.md#value-value).

#### `value: Value`

The value that has been checked and which the given check [`result`](resultcallback.md#result-boolean) applies.

#### `payload?: Payload`

Optional `payload` parameter passed to the function as additional data helpful for the check result.

### Returns

The **return value** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) indicating the check result of the given [`value`](resultcallback.md#value-value).
