---
description: The `CommonErrors` constructor
---

# v: Constructor

## `CommonErrors()`

Creates an instance of the errors storage with unique identification numbers.

{% code title="common-errors.class.ts" %}
```typescript
constructor(...id: Id[]) {
  Array.isArray(id) && (this.#id = new Set(id));
}
```
{% endcode %}

### Parameters

### Example usage
