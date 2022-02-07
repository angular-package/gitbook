# Generic type variables

## `Error<`<mark style="color:green;">`Id`</mark>`>` <a href="#wrap-opening" id="wrap-opening"></a>

#### <mark style="color:green;">`Id`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)`=`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)<mark style="color:green;">``</mark>

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided [`id`](../commonerror/v-constructor.md#id-id) indicates the identification type of a new [`Error`](broken-reference) instance.

{% code title="common-error.class.ts" %}
```typescript
class Error<
  Id extends string  // <--- Declare generic type variable Id.
> extends CommonError<Id> {
  ...
  constructor(
    problem: string,
    fix: string,
    id?: Id,  // <--- Capture generic type variable Id.
    template = Error.template
  ) { ... }
  ...
}
```
{% endcode %}