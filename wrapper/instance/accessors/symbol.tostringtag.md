# \[Symbol.toStringTag]

## `[Symbol.toStringTag]`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor, with the help of `toStringTag`, changes the default tag to `'wrapper'` in the [`Wrapper`](../../../wrap/info/#wrapper) instance. It can be read by the [`typeOf()`](https://type.angular-package.dev/v/type-draft/helper/typeof) function of [`@angular-package/type`](https://type.angular-package.dev).

{% code title="wrapper.class.ts" %}
```typescript
public get [Symbol.toStringTag](): string {
  return 'wrapper';
}
```
{% endcode %}

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
