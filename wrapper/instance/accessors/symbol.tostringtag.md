# \[Symbol.toStringTag]

## `[Symbol.toStringTag]`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor [`toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag) of the [`Symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol) changes the default tag `String` of the instance to the custom tag `Wrapper`. It can be read by the [`typeOf()`](https://type.angular-package.dev/v/type-draft/helper/typeof) function of [`@angular-package/type`](https://type.angular-package.dev).

{% code title="wrapper.class.ts" %}
```typescript
public get [Symbol.toStringTag](): string {
  return 'Wrapper';
}
```
{% endcode %}

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';
import { typeOf } from '@angular-package/type';

const quote = new Wrapper('[', ']', 'quote');

// Returns [object Wrapper].
Object.prototype.toString.call(quote);

// Returns wrapper.
typeOf(quote);
```
