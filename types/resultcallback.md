# ResultCallback

## `ResultCallback<Value, Payload>`

Represents a **callback function** with parameters, the [`value`](resultcallback.md#value-value) that has been checked, the [`result`](resultcallback.md#result-boolean) of this check, and an optional [`payload`](resultcallback.md#payload-payload).

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

A generic type variable `Value` determines [`value`](resultcallback.md#value-any) parameter type, by default [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any).

#### <mark style="color:green;">`Payload`</mark>`=`<mark style="color:green;">`object`</mark>

Generic type variable `Payload` indicates [`payload`](resultcallback.md#payload-payload) parameter type, by default [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object).

### Parameters

#### `result: boolean`

The check result of a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) type of the given [`value`](resultcallback.md#value-value).

#### `value: Value`

The value of the generic type variable [`Value`](resultcallback.md#value-any) to check and which the given check [`result`](resultcallback.md#result-boolean) applies.

#### `payload?: Payload`

An optional [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) of a generic type variable [`Payload`](resultcallback.md#payload-object) to provide more data.

### Returns

The **return value** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) indicating the check result of the given [`value`](resultcallback.md#value-value).
