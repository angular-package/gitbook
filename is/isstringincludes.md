# isStringIncludes()

### `isStringIncludes()`

Checks if any value is a `string` type or an instance of `String` by using `isString()` that includes all of the specified words/sentences.

{% code title="is-string-includes.func.ts" %}
```typescript
const isStringIncludes = <
  Type extends AnyString = string,
  Payload extends object = object
>(
  value: any,
  includes: string[],
  callback: ResultCallback<
    any,
    { includes: typeof includes } & Payload
  > = resultCallback,
  payload?: Payload
): value is Type =>
  callback(
    isString(value)
    ? isArray(includes)
      ? includes.every((include) => value.valueOf().includes(include))
      : false
    : false,
    value,
    { ...payload, includes, } as any
  );
```
{% endcode %}

### Parameters

| Name: type | Description |
| ---------- | ----------- |
|            |             |
|            |             |
|            |             |

### Returns

The return value is a `boolean` indicating whether the provided `value` is a `string` type or an instance of `String` that includes all of the specified words/sentences.

### Example usage

```typescript
// Example usage
import { isStringIncludes } from '@angular-package/type';

```

