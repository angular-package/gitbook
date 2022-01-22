# ResultCallback

### `ResultCallback<Value, Payload>`

Represents a callback function with parameters, the `value` that has been checked, the `result` of this check, and an optional `payload`.

{% code title="result-callback.type.ts" %}
```typescript
type ResultCallback<Value = any, Payload = object> = (
  result: boolean,
  value: Value,
  payload?: Payload
) => boolean;
```
{% endcode %}

