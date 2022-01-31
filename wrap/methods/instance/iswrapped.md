# isWrapped()

## `Wrap.prototype.isWrapped()`

The method checks whether the [primitive value](valueof.md) of the specified object is wrapped by the [opening](../../accessors/opening.md) and [closing](../../accessors/closing.md) chars of an instance or given [`opening`](iswrapped.md#opening-string-this.opening) and [`closing`](iswrapped.md#closing-string-this.closing) chars.

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

Optional opening chars of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type to check if the [primitive value](valueof.md) contains them at the **beginning**.

#### `closing: string = this.closing`

Optional closing chars of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type to check if the [primitive value](valueof.md) contains them at the **end**.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the object has both [`opening`](../../accessors/opening.md) and [`closing`](../../accessors/closing.md) chars or given [`opening`](iswrapped.md#opening-string-this.opening) and [`closing`](iswrapped.md#closing-string-this.closing) chars.

## Example usage

### Basic

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns true. Checks `[]`.
new Wrap(`[`, `]`, 'quote').isWrapped();

// Returns false.
// It's not wrapped cause of opening chars are an empty string.
new Wrap(``, `]`, 'quote').isWrapped();

// Returns false.
// It's not wrapped cause of closing chars are an empty string.
new Wrap(`[`, ``, 'quote').isWrapped();

// Returns false.
new Wrap(``, ``, 'quote').isWrapped();
```

### Given `opening`

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns true. Checks `[]`.
new Wrap(`[`, `]`, 'quote').isWrapped('[');

// Returns false.
new Wrap(`[`, `]`, 'quote').isWrapped('[', '');

// Returns false. Checks `<]`.
new Wrap(`[`, `]`, 'quote').isWrapped('<');

// Returns false.
// It's not wrapped cause of opening chars are an empty string.
new Wrap(``, `]`, 'quote').isWrapped('<');

// Returns false.
// It's not wrapped cause of closing chars are an empty string.
new Wrap(`[`, ``, 'quote').isWrapped('[');

// Returns false.
// It's not wrapped cause of closing chars are an empty string.
new Wrap(`[`, ``, 'quote').isWrapped('[', ''),
```

### Given `closing`

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns true. Checks `[]`.
new Wrap(`[`, `]`, 'quote').isWrapped(undefined, ']');

// Returns false. Checks `[>`.
new Wrap(`[`, `]`, 'quote').isWrapped(undefined, '>');

// Returns false.
// It's not wrapped cause of opening chars are an empty string.
new Wrap(``, `]`, 'quote').isWrapped(undefined, ']');

// Returns false.
// It's not wrapped cause of opening chars are an empty string.
new Wrap(``, `]`, 'quote').isWrapped(``, ']');
```

### Given `opening` and `closing` chars

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns false.
new Wrap(`[`, `]`, 'quote').isWrapped('[', ']');

// Returns false.
new Wrap(`[`, `]`, 'quote').isWrapped('[', '>');

// Returns false.
new Wrap(`[`, `]`, 'quote').isWrapped('<', ']');

// Returns false.
new Wrap(`[`, `]`, 'quote').isWrapped('<', '>');

// Returns false.
new Wrap(``, ``, 'quote').isWrapped('', '');
```
