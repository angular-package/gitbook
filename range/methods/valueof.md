---
description: >-
  Returns a read-only object consisting of the primitive values of `Minimum` and
  `Maximum` instances
---

# ⚠ valueOf()

## `Range.prototype.valueOf()`

{% hint style="danger" %}
**Deprecated**: This feature is no longer recommended. Avoid using it, and update existing code if possible. Be aware that this feature may cease to work at any time.
{% endhint %}

The `valueOf()` method returns a read-only object consisting of the primitive values of [`Minimum`](broken-reference) and [`Maximum`](broken-reference) instances.

{% code title="range.class.ts" %}
```typescript
public valueOf(): Readonly<{ min: Min; max: Max }> {
  return Object.freeze({
    min: this.#minimum.valueOf(),
    max: this.#maximum.valueOf(),
  });
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">`Readonly`</mark>`<{ min:`[<mark style="color:green;">`Min`</mark>](../generic-type-variables.md#minextendsnumber)`; max:`[<mark style="color:green;">`Max`</mark>](../generic-type-variables.md#maxextendsnumber)`; }>`

The **return type** is the [`Readonly`](https://www.typescriptlang.org/docs/handbook/utility-types.html#readonlytype) object consisting of property `min` of a generic type variable [`Min`](../generic-type-variables.md#minextendsnumber) and a `max` of generic type variable [`Max`](../generic-type-variables.md#maxextendsnumber).

### Returns

The **return value** is a frozen [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) consisting of the primitive values of [`Minimum`](broken-reference) and [`Maximum`](broken-reference) instances.&#x20;

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
const range = new Range(4, 27);

// Returns Readonly<{ min: 4; max: 27; }>
range.valueOf();
```
