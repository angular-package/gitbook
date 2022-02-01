# \[Symbol.toStringTag]

## `[Symbol.toStringTag]`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor [`toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag) of the [`Symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol) changes the default tag `String` of the instance to the custom tag `Wrap`. It can be read by the [`typeOf()`](https://type.angular-package.dev/v/type-draft/helper/typeof) function of [`@angular-package/type`](https://type.angular-package.dev).

{% code title="wrap.class.ts" %}
```typescript
public get [Symbol.toStringTag](): string {
  return 'wrap';
}
```
{% endcode %}

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';
import { typeOf } from '@angular-package/type';

// Define the wrap.
const tagWrap = new Wrap('[', ']');

// Returns [object Wrap].
Object.prototype.toString.call(tagWrap);

// Returns wrap.
typeOf(tagWrap);
```
