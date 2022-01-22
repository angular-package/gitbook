# ForEachCallback

### `ForEachCallback<Value, Payload>`

Represents a callback function of `forEach()` method which is executed once for each element.

{% code title="foreach-callback.type.ts" %}
```typescript
type ForEachCallback<Value = any, Payload = object> = (
  result: boolean,
  value: Value,
  index: number,
  array: any[],
  payload?: Payload
) => void;
```
{% endcode %}

