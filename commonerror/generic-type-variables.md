# Generic type variables

## `CommonError<`<mark style="color:green;">`Id`</mark>`>` <a href="#wrap-opening" id="wrap-opening"></a>

#### <mark style="color:green;">`Id`</mark>`extends`<mark style="color:green;">`string`</mark>`=`<mark style="color:green;">`string`</mark>

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided [`opening`](broken-reference) indicates the opening type of a new [`Wrap`](broken-reference) instance.

{% code title="wrap.class.ts" %}
```typescript
class Wrap<
  Opening extends string = string, // <--- Declare generic type variable Opening.
  Text extends string = ``,
  Closing extends string = string
> extends String {
  ...
  constructor(
    opening: Opening, // <--- Capture generic type variable Opening.
    closing: Closing,
    text: Text = '' as Text
  ) { ... }
  ...
}
```
{% endcode %}

