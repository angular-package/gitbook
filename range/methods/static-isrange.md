---
description: >-
  Checks whether the value is an instance of `Range` of any or the given
  minimum, maximum, and step
---

# static isRange()

## `Range.isRange()`

The static `isRange()` method checks whether the [`value`](static-isrange.md#value-any) is an instance of [`Range`](broken-reference) of any or the given [**minimum**](static-isrange.md#min-min), [**maximum**](static-isrange.md#max-max) range and [step](static-isrange.md#step-step).

{% code title="range.class.ts" %}
```typescript
public static isRange<
  Min extends number,
  Max extends number,
  Step extends number
>(
  value: any,
  min?: Min,
  max?: Max,
  step?: Step
): value is Range<Min, Max, Step> {
  return typeof value === 'object' && value instanceof this
    ? (typeof min === 'number' ? value.min === min : true) &&
        (typeof max === 'number' ? value.max === max : true) &&
        (typeof step === 'number' ? value.step === step : true)
    : false;
}
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Min`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value **captured** from the supplied [`min`](static-isrange.md#min-min) indicates the **minimum** range type via the [return type](static-isrange.md#return-type).

#### <mark style="color:green;">`Max`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value **captured** from the supplied [`max`](static-isrange.md#max-max) indicates the **maximum** range type via the [return type](static-isrange.md#return-type).

#### <mark style="color:green;">`Step`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)

A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value equal to **`1`**, optionally **captured** from the supplied [`step`](static-isrange.md#step-step) indicates the range step type via [return type](static-isrange.md#return-type).

### Parameters

#### `value:`[<mark style="color:green;">`any`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#any)<mark style="color:green;">``</mark>

The value of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type to test against the [`Range`](broken-reference) instance.

#### `min?:`[<mark style="color:green;">`Min`</mark>](static-isrange.md#minextendsnumber)<mark style="color:green;">``</mark>

The optional **minimum** range of generic type variable [`Min`](static-isrange.md#minextendsnumber) to check whether it's equal to a **minimum** of the given [`value`](static-isrange.md#value-any).

#### `max?:`[<mark style="color:green;">`Max`</mark>](static-isrange.md#minextendsnumber-1)<mark style="color:green;">``</mark>

The optional **maximum** range of generic type variable [`Max`](static-isrange.md#maxextendsnumber) to check whether it's equal to a **maximum** of the given [`value`](static-isrange.md#value-any).

#### `step?:`[<mark style="color:green;">`Step`</mark>](static-isrange.md#stepextendsnumber-1)<mark style="color:green;">``</mark>

Optional step of generic type variable [`Step`](static-isrange.md#stepextendsnumber) to check whether it's equal to the step of the given [`value`](static-isrange.md#value-any).

### Return type

#### `value is`[<mark style="color:green;">`Range`</mark>](broken-reference)`<`[<mark style="color:green;">`Min`</mark>](static-isrange.md#minextendsnumber)`,`[<mark style="color:green;">`Max`</mark>](static-isrange.md#maxextendsnumber)`,`[<mark style="color:green;">`Step`</mark>](static-isrange.md#stepextendsnumber)`>`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) resulting from its statement indicating the [`value`](static-isrange.md#value-any) is the [`Range`](broken-reference) object that takes the generic type variable [`Min`](static-isrange.md#minextendsnumber), [`Max`](static-isrange.md#maxextendsnumber) and [`Step`](static-isrange.md#stepextendsnumber).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](static-isrange.md#value-any) is an instance of [`Range`](broken-reference) of any or the given [minimum](static-isrange.md#min-min), [maximum](static-isrange.md#max-max) range and [`step`](static-isrange.md#step-step).

## Example usage

```typescript
// Example usage.
import { Range } from '@angular-package/range';

// Create new instance.
const range = new Range(4, 27, 1.5);

// Returns true of type value is Range<number, number, number>
Range.isRange(range);

// Returns true of type value is Range<4, number, number>
Range.isRange(range, 4);

// Returns true of type value is Range<4, 27, number>
Range.isRange(range, 4, 27);

// Returns true of type value is Range<4, 27, 1.5>
Range.isRange(range, 4, 27, 1.5);

// Returns false of type value is Range<3, number, number>
Range.isRange(range, 3);

// Returns false of type value is Range<3, 26, number>
Range.isRange(range, 3, 26);

// Returns false of type value is Range<3, 26, 1.0>
Range.isRange(range, 3, 26, 1.0);

// Returns true of type value is Range<number, 27, number>
Range.isRange(range, undefined, 27);

// Returns true of type value is Range<number, number, 1.5>
Range.isRange(range, undefined, undefined, 1.5);
```
