# isWrapped()

## `Wrap.prototype.isWrapped()`

The method checks whether the primitive value of the specified object is wrapped by the [opening](../../accessors/#wrap.prototype.opening) and [closing](../../accessors/#wrap.prototype.closing) chars of an instance or given opening and closing chars.

{% code title="wrap.class.ts" %}
```typescript
public isWrapped(
  opening: string = this.opening,
  closing: string = this.closing
): boolean {
  return this.hasOpening(opening) && this.hasClosing(closing);
}
```
{% endcode %}

### Parameters

#### `opening: string = this.opening`

Optional opening chars of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type to check if the text contains them at the beginning.

#### `closing: string = this.closing`

Optional closing chars of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type to check if the text contains them at the end.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the object has both opening and closing chars.

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns true.
new Wrap(`[`, `]`, 'quote').isWrapped();

// Returns true.
new Wrap(`[`, `]`, 'quote').isWrapped('[');

// Returns true.
new Wrap(`[`, `]`, 'quote').isWrapped(undefined, ']');

// Returns false.
new Wrap(`[`, `]`, 'quote').isWrapped('<');

// Returns false.
new Wrap(`[`, `]`, 'quote').isWrapped(undefined, '>');

// Returns false.
new Wrap(`[`, `]`, 'quote').isWrapped('<', '>');

// Returns false.
new Wrap(``, ``, 'quote').isWrapped();

// Returns false.
new Wrap(``, ``, 'quote').isWrapped('', '');
```
