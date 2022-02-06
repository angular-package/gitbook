# message

## `CommonError.prototype.message`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the error [message](../../../getting-started/basic-concepts.md#message) by returning the parent [`message`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Error/message) property of the [`Error`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Error) object.

{% code title="common-error.class.ts" %}
```typescript
public get message(): string {
  return super.message;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;"></mark>[<mark style="color:green;">string</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)<mark style="color:green;"></mark>

### Returns

The **return value** is the error [message](../../../getting-started/basic-concepts.md#message) of a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type.

## Example usage

```typescript
// Example usage.
import { CommonError } from '@angular-package/error';


```

