# typeOf()

### `typeOf()`

Gets the specific object type of any value.

{% code title="type-of.func.ts" %}
```typescript
const typeOf = (value: any): string =>
  Object.prototype.toString.call(value).slice(8, -1).toLowerCase();
```
{% endcode %}

### Parameters

#### `value: any`

### Returns



### Example usage

```
// Some code
```
