---
description: The errors storage of the Map type
---

# #errors

## `#errors`

The errors storage of the [`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Map) type where the `key` is of the generic type variable [`Id`](../v-generic-type-variables.md).

{% code title="common-errors.class.ts" %}
```typescript
#errors: Map<Id, any> = new Map();
```
{% endcode %}

### Type

#### `Map<`[<mark style="color:green;">`Id`</mark>](../v-generic-type-variables.md#wrap-opening)`,`[<mark style="color:green;">`any`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#any)`>`
