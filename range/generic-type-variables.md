---
description: The `Range` object generic type variables
---

# r: Generic type variables

### `Range<`<mark style="color:green;background-color:green;">`Min`</mark>`,`<mark style="color:green;">`Max`</mark>`,`<mark style="color:green;">`Step`</mark>`>`

#### <mark style="color:green;">`Min`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

​A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value **captured** from the supplied [`min`](constructor.md#min-min) indicates the minimum range type of a new [`Range`](broken-reference) instance.

{% code title="range.class.ts" %}
```typescript
class Range<
  Min extends number, // <--- Declare generic type variable Min.
  Max extends number,
  Step extends number = 1
> {
  constructor(
    min: Min, // <--- Capture generic type variable Min.
    max: Max,
    value?: number,
    step: Step = 1 as Step
  ) { }
}
```
{% endcode %}

### `Range<`<mark style="color:green;">`Min`</mark>`,`<mark style="color:green;background-color:green;">`Max`</mark>`,`<mark style="color:green;">`Step`</mark>`>`

#### <mark style="color:green;">`Max`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)<mark style="color:green;">``</mark>

A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value **captured** from the supplied [`max`](constructor.md#max-max) indicates the maximum range type of a new [`Range`](broken-reference) instance.

```typescript
class Range<
  Min extends number,
  Max extends number, // <--- Declare generic type variable Max.
  Step extends number = 1
> {
  constructor(
    min: Min,
    max: Max, // <--- Capture generic type variable Max.
    value?: number,
    step: Step = 1 as Step
  ) {}
}
```

### `Range<`<mark style="color:green;">`Min`</mark>`,`<mark style="color:green;">`Max`</mark>`,`<mark style="color:green;background-color:green;">`Step`</mark>`>`

#### <mark style="color:green;">`Step`</mark>`extends`[<mark style="color:green;">`number`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)`= 1`

A generic type variable constrained by the [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number), by default of the value equal to `1`, optionally **captured** from the supplied [`step`](constructor.md#step-step) indicates the range step type of a new [`Range`](broken-reference) instance.

```typescript
class Range<
  Min extends number,
  Max extends number,
  Step extends number = 1 // <--- Declare generic type variable Step.
> {
  constructor(
    min: Min,
    max: Max,
    value?: number,
    step: Step = 1 as Step // <--- Capture generic type variable Step.
  ) { }
}
```
