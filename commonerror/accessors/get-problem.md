# get problem()

## `CommonError.prototype.problem`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the [problem](../../getting-started/basic-concepts.md#problem) by returning the [`#problem`](../properties/problem.md) property of a specified object.

{% code title="common-error.class.ts" %}
```typescript
public get problem(): string {
  return this.#problem;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;">``</mark>[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)<mark style="color:green;">``</mark>

### Returns

The **return value** is the [problem](../../getting-started/basic-concepts.md#problem) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

## Example usage

```typescript
// Example usage.
import { CommonError } from '@angular-package/error';

// Extend the `CommonError` class.
class TestError extends CommonError {}

// Returns "Problem accessor."
new TestError('Problem accessor.', 'Fix accessor.', '(AE:427)').problem;
```

