# Constructor

## `CommonError()`

Creates an instance that represents an error with the described problem and its solution, optionally with expected type, range, an explicit identification, and an error message template.

{% code title="common-error.class.ts" %}
```typescript
constructor(
  problem: string,
  fix: string,
  id?: Id,
  template = CommonError.template,
  additional?: { min?: number; max?: number; type?: string }
) {
  super(
    CommonError.defineMessage`${problem}${fix}${id}${template}${additional}`
  );
  this.#fix = fix;
  this.#id = id;
  this.#problem = problem;
  this.#template = template;
}
```
{% endcode %}

### Parameters

#### problem: [<mark style="color:green;">string</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;"></mark>

Description of the problem of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### fix: [<mark style="color:green;">string</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String)<mark style="color:green;"></mark>

A solution to the given [`problem`](constructor.md#problem-string) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

#### id?: [<mark style="color:green;">Id</mark>](generic-type-variables.md#wrap-opening)<mark style="color:green;"></mark>

Optional unique identification to the given [`problem`](constructor.md#problem-string) of generic type variable [`Id`](generic-type-variables.md#wrap-opening).

#### template: [<mark style="color:green;">string</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) = <mark style="color:green;">CommonError</mark>.template

A template of error message with the replaceable [`{problem}`](constructor.md#problem), [`{fix}`](constructor.md#fix) and optional [`{id}`](constructor.md#id), [`{max}`](constructor.md#max), [`{min}`](constructor.md#min) and [`{type}`](constructor.md#type) tags. By default, the value is equal to the static property [`template`](properties/static-template.md).

#### additional: { min?: [<mark style="color:green;">number</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number); max?: [<mark style="color:green;">number</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number); <mark style="color:green;"></mark> type?: [<mark style="color:green;">string</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String); }

An optional object consists of optional `min`, `max`, and `type` properties to define the error message.&#x20;

`max` - The maximum number replaceable on the template as `{max}` tag.\
`min` - The minimum number is replaceable on the template as `{min}` tag.\
`type` The type indicates the expected type that isn't throwing an error or the not expected type that is throwing an error.

## Tags

Replaceable tags on the [`template`](constructor.md#template-string-commonerror.template).

#### `{problem}`

Replaceable by the given required [`problem`](constructor.md#problem-string) parameter.

#### `{fix}`

Replaceable by the given required [`fix`](constructor.md#fix-string) parameter.

#### `{id}`

Replaceable by the given [`id`](constructor.md#id-id) parameter.

#### `{max}`

Replaceable by the property `max` of the given [`additional`](constructor.md#optional-min-number-max-number-type-string) parameter.

#### `{min}`

Replaceable by the property `min` of the given [`additional`](constructor.md#optional-min-number-max-number-type-string) parameter.

#### `{type}`

Replaceable by the property `type` of the given [`additional`](constructor.md#optional-min-number-max-number-type-string) parameter.

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
