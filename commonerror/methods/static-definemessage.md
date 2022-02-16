---
description: The static "tag" method builds from the given values the error message
---

# static defineMessage()

## `CommonError.defineMessage()`

The static "[tag](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template\_literals)" method builds from the given [`values`](static-definemessage.md#...values-any) the error message of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type on the template.

{% code title="common-error.class.ts" %}
```typescript
protected static defineMessage(
  templateStringsArray: TemplateStringsArray,
  ...values: any[]
): string {
  let problem: string,
    fix: string,
    id: string | undefined,
    template: string,
    additional: { link?: string; min?: number; max?: number; type?: string };
  [problem, fix, id, template, additional] = values;
  template = (template || CommonError.template)
    .replace('{problem}', problem || '')
    .replace(/{id}/g, id || '')
    .replace(/{link}/g, additional?.link ? additional.link : '')
    .replace(/{max}/g, additional?.max ? String(additional.max) : '')
    .replace(/{min}/g, additional?.min ? String(additional.min) : '')
    .replace(/{type}/g, additional?.type ? additional.type : '')
    .replace('{fix}', fix || '');
  return template;
}
```
{% endcode %}

### Parameters

#### `templateStringsArray:`<mark style="color:green;">`TemplateStringsArray`</mark>

\-

#### `...values:`[<mark style="color:green;">`any`</mark>](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any)`[]`

A rest parameter of expressions in order [`${problem}`](../constructor.md#problem-string), [`${fix}`](../constructor.md#fix-string), [`${id}`](../constructor.md#id-id), [`${template}`](../constructor.md#template-string-commonerror.template) and [`${additional}`](../constructor.md#additional-link-string-min-number-max-number-type-string).

### Returns

The re**turn value** is the error message of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type created from the expressions given in the [`values`](static-definemessage.md#...values-any).

## Example usage

```typescript
// Example usage.
import { CommonError } from '@angular-package/error';

const problem = 'The given `age` parameter must be';
const fix = 'Provided string type is not accepted, change to ';
const id = 'AE: 427';
const template = `Issue({id}): {problem} of {type} between range {min} and {max}. {fix}{type}`;
const additional = { max: 27, min: 9, type: 'number' };

class TestError<Id extends string> extends CommonError<Id> {
  public static isError<Id extends string>(
    value: any,
    id?: Id
  ): value is CommonError<Id> {
    return super.isError(value, id);
  }

  public static defineMessage(
    templateStringsArray: TemplateStringsArray,
    ...values: any[]
  ): string {
    return super.defineMessage(templateStringsArray, ...values);
  }
}

// Returns
// Issue(AE: 427): The given `age` parameter must be of number between range 9 and 27. Provided string type is not accepted, change to number
TestError.defineMessage`${problem}${fix}${id}${template}${additional}`;
```
