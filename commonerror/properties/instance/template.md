# #template

## `#template`

A [string-type](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) privately stored [template](../../../getting-started/basic-concepts.md#template) of the error [message](../../../getting-started/basic-concepts.md#message) that contains replaceable required [`{fix}`](../../constructor.md#fix), [`{problem}`](../../constructor.md#problem) and optional [`{id}`](../../constructor.md#id), [`{max}`](../../constructor.md#max), [`{min}`](../../constructor.md#min), [`{type}`](../../constructor.md#type) tags.

{% code title="common-error.class.ts" %}
```typescript
#template: string;
```
{% endcode %}

## Example usage

```typescript
// Example usage.
import { CommonError } from '@angular-package/error'; 


```
