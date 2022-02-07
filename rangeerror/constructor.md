# Constructor

## `RangeError()`

Creates the `Error` instance that represents an error with the message built of the described [problem](constructor.md#problem-string) and its [solution](constructor.md#fix-string), optionally marked with an explicit [identification](constructor.md#id-id) on the given or stored [template](constructor.md#template-string-error.template).

{% code title="error.class.ts" %}
```typescript
constructor(
  problem: string,
  fix: string,
  id?: Id,
  template = Error.template
) {
  super(problem, fix, id, template);
}
```
{% endcode %}

### Parameters

#### problem: [<mark style="color:green;">string</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;"></mark>

Description of the problem of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### fix: [<mark style="color:green;">string</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;"></mark>

A solution to the given [`problem`](constructor.md#problem-string) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### id?: [<mark style="color:green;">Id</mark>](../commonerror/generic-type-variables.md#wrap-opening)<mark style="color:green;"></mark>

Optional unique identification to the given [`problem`](constructor.md#problem-string) of generic type variable [`Id`](../commonerror/generic-type-variables.md#wrap-opening).

#### template: [<mark style="color:green;">string</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) = <mark style="color:green;">Error</mark>.template

A template of the error message of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with the replaceable [`{problem}`](../commonerror/v-constructor.md#problem), [`{fix}`](../commonerror/v-constructor.md#fix) and optional [`{id}`](../commonerror/properties/static-template.md#id), [`{max}`](../commonerror/properties/static-template.md#max), [`{min}`](../commonerror/properties/static-template.md#min), [`{type}`](../commonerror/properties/static-template.md#type) tags. By default, the value is equal to the static property [`RangeError.template`](properties/static-template.md).
