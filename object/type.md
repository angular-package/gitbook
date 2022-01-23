# type {}

## `type {}`

A frozen `object` that consists of `is`, `are`, and `guard` objects.

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

The `object` consists of `are` functions.

#### `guard`

The `object` consists of `guard` functions.

#### `is`

The `object` consists of `is` functions.

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
