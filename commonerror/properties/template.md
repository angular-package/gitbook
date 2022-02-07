---
description: >-
  A string-type privately stored template of the error message that contains
  replaceable required `{fix}`, `{problem}` and optional `{id}`, `{max}`,
  `{min}`, `{type}` tags.
---

# #template

## `#template`

A [string-type](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) privately stored [template](../../getting-started/basic-concepts.md#template) of the error [message](../../getting-started/basic-concepts.md#message) that contains replaceable required [`{fix}`](../v-constructor.md#fix), [`{problem}`](../v-constructor.md#problem) and optional [`{id}`](../v-constructor.md#id), [`{max}`](../v-constructor.md#max), [`{min}`](../v-constructor.md#min), [`{type}`](../v-constructor.md#type) tags.

{% code title="common-error.class.ts" %}
```typescript
#template: string;
```
{% endcode %}
