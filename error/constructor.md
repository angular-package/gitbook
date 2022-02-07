# Constructor

## `Error()`

The `Error` object is an extension of the [`CommonError`](broken-reference) class and is thrown when a runtime error occurs with a [message](../commonerror/accessors/get-message.md) built from a [solution](constructor.md#fix-string) to the described [problem](constructor.md#problem-string) but with additional [identification](constructor.md#id-id), on the [template](constructor.md#template-string-error.template).

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

A template of error message with the replaceable [`{problem}`](constructor.md#problem), [`{fix}`](constructor.md#fix) and optional [`{id}`](constructor.md#id), [`{max}`](constructor.md#max), [`{min}`](constructor.md#min) and [`{type}`](constructor.md#type) tags. By default, the value is equal to the static property [`template`](../commonerror/properties/static-template.md).

## Example usage

```typescript
// Example usage.
import { Error } from '@angular-package/error';


```