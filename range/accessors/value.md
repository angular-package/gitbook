---
description: >-
  The `value` accessor indicates the range current value of the number type of a
  specified `Range` object
---

# value?

## `Range.prototype.value`

The `value` accessor indicates the range current value of the [number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type of a specified [`Range`](broken-reference) object.

### `get`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor retrieves the [`#value`](../properties/value.md#value) property that indicates the range current value of the [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type of a specified [`Range`](broken-reference) object. It can be set by the [`setValue()`](../methods/setvalue.md#range.prototype.setvalue) method.

{% code title="range.class.ts" %}
```typescript
public get value(): number | undefined {
  return this.#value;
}
```
{% endcode %}

### `set`

The [`set`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/set) accessor sets the range current value of the [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type between the [minimum](../properties/min.md#range.prototype.min) and [maximum](../properties/max.md#range.prototype.max) of a specified [`Range`](broken-reference) object.

{% code title="range.class.ts" %}
```typescript
public set value(value: number | undefined) {
  typeof value === 'number'
    ? this.has(value) && (this.#value = value)
    : undefined;
}
```
{% endcode %}

### Type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`|`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;">``</mark>

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
// Returns Range {min: -27, max: 27, value: 11} of Range<4, 27, 1>.
const range = new Range(-27, 27, 11);

// Returns 11 of type number | undefined.
range.value;

// Sets below minimum.
range.value = -28;

// Returns 11. Nothing was changed.
range.value;

// Sets above maximum.
range.value = 28;

// Returns 11. Nothing was changed.
range.value;
```
