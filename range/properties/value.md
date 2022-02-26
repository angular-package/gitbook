---
description: >-
  The optional read-only `value` property indicates the range current value of
  the `number` type between the minimum and maximum of a specified `Range`
  object
---

# value?

## `Range.prototype.value`

The optional read-only `value` property indicates the range current value of the [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type between the [minimum](min.md#range.prototype.min) and [maximum](max.md) of a specified [`Range`](broken-reference) object. Despite it being a read-only property, it can be set by the [`setValue()`](../methods/setvalue.md#range.prototype.setvalue) method because it checks whether the value is between the range of a specified object before the set.

{% code title="range.class.ts" %}
```typescript
public readonly value?: number;
```
{% endcode %}

### Type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`|`[<mark style="color:green;">`undefined`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined)<mark style="color:green;">``</mark>

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
// Returns Range {min: 4, max: 27, value: 11} of Range<4, 27, 1>.
const range = new Range(4, 27, 11);

// Returns 11 of type number | undefined.
range.value;
```
