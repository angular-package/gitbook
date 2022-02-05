# hasClosing()

## `Wrap.prototype.hasClosing()`

Checks whether the [primitive value](valueof.md) of a specified object has the [`closing`](../../accessors/instance/closing.md) chars or given [`closing`](hasclosing.md#closing-string) chars.

{% hint style="info" %}
If given `closing` chars in the constructor are the **empty** `string`, the method returns **`false`**.
{% endhint %}

{% code title="wrap.class.ts" %}
```typescript
public hasClosing(closing?: string): boolean {
  return (
    this.#closing.length >= 1 &&
    (typeof closing === 'string' ? this.#closing === closing : true)
  );
}
```
{% endcode %}

### Parameters

#### `closing?: string`

Optional closing chars of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type to check whether the [primitive value](valueof.md) contains them at the **end**.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [primitive value](valueof.md) has the [`closing`](../../accessors/instance/closing.md) chars or given [`closing`](hasclosing.md#closing-string) chars.

## Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Returns true.
new Wrap(`[`, `]`, 'quote').hasClosing();

// Returns false.
new Wrap(`[`, ``, 'quote').hasClosing();
```

### Given `closing` chars

```typescript
// Example usage of given closing chars.
import { Wrap } from '@angular-package/wrapper';

// Returns true.
new Wrap(`[`, `]`, 'quote').hasClosing(']');

// Returns false.
new Wrap(`[`, `]`, 'quote').hasClosing('');

// Returns false.
new Wrap(`[`, ``, 'quote').hasClosing('');

// Returns false.
new Wrap(`[`, ``, 'quote').hasClosing(']');
```
