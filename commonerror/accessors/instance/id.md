# id

## `CommonError.prototype.id`

The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the error [identification](../../../getting-started/basic-concepts.md#identification) by returning the [`#id`](../../properties/instance/id.md) property of a specified object.

{% code title="common-error.class.ts" %}
```typescript
public get id(): Id | undefined {
  return this.#id;
}
```
{% endcode %}

### Return type

#### <mark style="color:green;"></mark>[<mark style="color:green;">Id</mark>](../../generic-type-variables.md#wrap-opening) | [<mark style="color:green;">undefined</mark>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined)<mark style="color:green;"></mark>

The **return type** is the generic type variable [`Id`](../../generic-type-variables.md#wrap-opening) or [`undefined`](https://www.typescriptlang.org/docs/handbook/basic-types.html#null-and-undefined).

### Returns

The **return value** is the error [identification](../../../getting-started/basic-concepts.md#identification) of the generic type variable [`Id`](../../generic-type-variables.md#wrap-opening) or [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined).

## Example usage

```typescript
// Example usage.
import { CommonError } from '@angular-package/error';


```

