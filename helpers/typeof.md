# typeOf()

## `typeOf()`

Gets the specific object type of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) value.

{% code title="type-of.func.ts" %}
```typescript
const typeOf = (value: any): string =>
  Object.prototype.toString.call(value).slice(8, -1).toLowerCase();
```
{% endcode %}

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to obtain its class name.

### Returns

The **return value** is the object prototype class name of the given [`value`](typeof.md#value-any).

### Example usage

```typescript
// Example usage.
import { typeOf } from '@angular-package/type';

```
