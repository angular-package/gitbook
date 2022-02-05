# hasOpening()

## `Wrap.prototype.hasOpening()`

Checks whether the [primitive value](valueof.md) of a specified object has the [`opening`](../../accessors/instance/opening.md) chars or given [`opening`](hasopening.md#opening-string) chars.

{% hint style="info" %}
If given `opening` chars in the constructor are the **empty** `string`, the method returns **`false`**.
{% endhint %}

{% code title="wrap.class.ts" %}
```typescript
public hasOpening(opening?: string): boolean {
  return (
    this.#opening.length >= 1 &&
    (typeof opening === 'string' ? this.#opening === opening : true)
  );
}
```
{% endcode %}

### Parameters

#### `opening?: string`

Optional opening chars of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type to check if the [primitive value](valueof.md) contains them at the **beginning**.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [primitive value](valueof.md) has the [`opening`](../../accessors/instance/opening.md) chars or given [`opening`](hasopening.md#opening-string) chars.

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns true.
new Wrap(`[`, `]`, 'quote').hasOpening();

// Returns false.
new Wrap(``, `]`, 'quote').hasOpening();
```

### Given `closing` chars

```typescript
// Example usage of given opening chars.
import { Wrap } from '@angular-package/wrapper';

// Returns true.
new Wrap(`[`, `]`, 'quote').hasOpening('[');

// Returns false.
new Wrap(`[`, `]`, 'quote').hasOpening('');

// Returns false.
new Wrap(``, `]`, 'quote').hasOpening('');

// Returns false.
new Wrap(``, `]`, 'quote').hasOpening('[');
```
