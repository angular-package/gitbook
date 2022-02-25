---
description: Creates the `Range` instance from the given random numbers and the step
---

# static createFrom()

## `Range.createFrom()`

Creates the [`Range`](broken-reference) instance from the given random [`numbers`](static-createfrom.md#numbers-number) and the [`step`](static-createfrom.md#step-step).

{% code title="range.class.ts" %}
```typescript
public static createFrom<Step extends number = 1>(
  numbers: number[],
  step: Step = 1 as Step
): Range<number, number, Step> {
  return Range.create(
    Math.min.apply(0, numbers),
    Math.max.apply(0, numbers),
    step
  );
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Step`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`= 1`

A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value equal to **`1`**, optionally **captured** from the supplied [`step`](static-createfrom.md#step-step) indicates the range step type of a new [`Range`](broken-reference) instance.

### Parameters

#### `numbers:`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`[]`

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of numbers to find a range and create a new instance.

#### `step:`<mark style="color:green;">`Step`</mark>

Optional step of generic type variable [`Step`](static-createfrom.md#stepextendsnumber-1) to set with a new [`Range`](broken-reference) instance, by default **`1`**.

### Return type

#### ``[<mark style="color:green;">`Range`</mark>](broken-reference)`<`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`,`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`,`[<mark style="color:green;">`Step`</mark>](static-createfrom.md#stepextendsnumber-1)`>`

The **return type** is the [`Range`](broken-reference) object that takes generic type variable [`Step`](static-createfrom.md#stepextendsnumber-1).

### Returns

The **return value** is the [`Range`](broken-reference) instance created from the given required random [numbers](static-createfrom.md#numbers-number) and the optional [step](static-createfrom.md#step-step).

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Returns Range {min: 4, max: 27} of type Range<number, number, 1>.
Range.createFrom([12, 14, 5, 23, 14, 27, 17, 4, 11, 12]);

// Returns Range {min: 4, max: 27} of type Range<number, number, 1.5>.
Range.createFrom([12, 14, 5, 23, 14, 27, 17, 4, 11, 12]);
```
