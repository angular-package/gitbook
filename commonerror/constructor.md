# Constructor

## `CommonError()`

Creates an error instance with the [message](accessors/get-message.md) built from the given [problem](accessors/get-problem.md), its [solution](accessors/get-fix.md), optional [type](constructor.md#additional-min-number-max-number-type-string), [range](constructor.md#additional-min-number-max-number-type-string), an explicit [identification](constructor.md#id-id) on the supplied or stored [template](constructor.md#template-string-commonerror.template).

{% code title="common-error.class.ts" %}
```typescript
constructor(
  problem: string,
  fix: string,
  id?: Id,
  template = CommonError.template,
  additional?: { link?: string; max?: number; min?: number; type?: string }
) {
  super(
    CommonError.defineMessage`${problem}${fix}${id}${template}${additional}`
  );
  this.#fix = fix;
  this.#id = id;
  this.#link = additional?.link;
  this.#problem = problem;
  this.#template = template;
}
```
{% endcode %}

### Parameters

#### `problem:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

Description of the problem of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `fix:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;">``</mark>

A solution to the given [`problem`](constructor.md#problem-string) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### `id?:`[<mark style="color:green;">`Id`</mark>](generic-type-variables.md#wrap-opening)<mark style="color:green;">``</mark>

Optional unique [identification](../getting-started/basic-concepts.md#identification) to the given [`problem`](constructor.md#problem-string) of generic type variable [`Id`](generic-type-variables.md#commonerror-less-than-id-greater-than).

#### `template:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)`=`<mark style="color:green;">`CommonError`</mark>`.template`

A template of error message with the replaceable [`{problem}`](constructor.md#problem), [`{fix}`](constructor.md#fix) and optional [`{id}`](constructor.md#id), [`{max}`](constructor.md#max), [`{min}`](constructor.md#min) and [`{type}`](constructor.md#type) tags. By default, the value is equal to the static property [`template`](properties/static-template.md).

#### `additional: { link?:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)`; min?:`[<mark style="color:green;">`number`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number)`; max?:`[<mark style="color:green;">`number`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number)`; type?:`[<mark style="color:green;">`string`</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)`}`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) consists of optional `link`, `min`, `max`, and `type` properties to define the error [`message`](accessors/get-message.md).&#x20;

`link` - The link to read more about the thrown error replaceable on the given [`template`](constructor.md#template-string-commonerror.template) as [`{link}`](properties/static-template.md#link) tag.\
`max`    - The maximum number replaceable on the given [`template`](constructor.md#template-string-commonerror.template) as [`{max}`](properties/static-template.md#max) tag.\
`min`   - The minimum number is replaceable on the given [`template`](constructor.md#template-string-commonerror.template) as [`{min}`](properties/static-template.md#min) tag.\
`type` - The type indicates the expected type that isn't throwing an error or the not expected type that is throwing an error replaceable on the given [`template`](constructor.md#template-string-commonerror.template) as the [`{type}`](properties/static-template.md#type) tag.

## Example usage

### Basic usage

```typescript
// Example usage.
import { CommonError } from '@angular-package/error';

class TestError extends CommonError {}

// Returns Error: Problem: problem => Fix: fix
new TestError('problem', 'fix');
```

### Parameter `id` and `template`

```typescript
// Example usage.
import { CommonError } from '@angular-package/error';

class TestError extends CommonError {}

// Returns Error: Problem(AE:427): problem => Fix: fix
new TestError('problem', 'fix', '(AE:427)');

// Returns Error: problem(AE:427). fix
new TestError('problem', 'fix', 'AE:427', '{problem}({id}). {fix}');
```

### Parameter `additional`

```typescript
// Example usage.
import { CommonError } from '@angular-package/error';

class TestError extends CommonError {}

// Returns Error: (AE:427)Age must be above 9. Provide age more than 9
new TestError(
  'Age must be above ', // Problem
  'Provide age more than ', // Fix
  'AE:427', // Identification
  '({id}){problem}{min}. {fix}{min}', // Template
  { min: 9 } // Additional
);

// Returns 
// Error: (AE:427)The `age` parameter is 45. Provided `age` must be between 9 and 12
new TestError(
  'The `age` parameter is 45.', // Problem
  'Provided `age` must be', // Fix
  'AE:427', // Identification
  '({id}){problem} . {fix} between {min} and {max}', // Template
  { min: 9, max: 12 } // Additional
);

// Returns
// Error: (AE:427)The `age` parameter is not a number. Provided `age` must be a
// number between 9 and 12.
new TestError(
  'The `age` parameter is not a', // Problem
  'Provided `age` must be a ', // Fix
  'AE:427', // Identification
  '({id}){problem} {type}. {fix} {type} between {min} and {max}.', // Template
  { min: 9, max: 12, type: 'number' } // Additional
);
```
