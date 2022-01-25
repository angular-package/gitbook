# type {}

## `type {}`

A frozen [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) that consists of [`is`](is-is.md), [`are`](are-are.md), and [`guard`](../guard/guard-guard.md) objects.

{% code title="type.object.ts" %}
```typescript
const type = Object.freeze({
  are,
  is,
  guard
});
```
{% endcode %}

### Properties

#### `are`

The [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) consists of **are** functions.

#### `guard`

The [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) consists of **guard** functions.

#### `is`

The [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) consists of **is** functions.

### Example usage

```typescript
// Example usage.
import { type } from '@angular-package/type';

// `is` functions
type.is.boolean(true); // true, value is boolean
type.is.array(true); // false, value is any[]

// `guard` functions
type.guard.number(3); // true, value is number
```
