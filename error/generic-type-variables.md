# Generic type variables

## `Error<`<mark style="color:green;background-color:green;">`Id`</mark>`>` <a href="#wrap-opening" id="wrap-opening"></a>

#### <mark style="color:green;">`Id`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)

​A generic type variable constrained by the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String), by default of the value **captured** from the provided [`id`](constructor.md#id-id) indicates the [identification](../getting-started/basic-concepts.md#identification) type of a new [`Error`](broken-reference) instance.

{% code title="error.class.ts" %}
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
