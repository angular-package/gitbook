# replaceOpening()

### `Wrapper.replaceOpening()`

Replaces the opening chars in a given `text` with a given replacement value at the beginning of the **text**.

{% code title="wrapper.class.ts" %}
```typescript
public static replaceOpening(
  text: string,
  opening: string,
  replaceValue: string
): string {
  return this.hasOpening(text, opening)
    ? text.replace(opening, String(replaceValue))
    : text;
}
```
{% endcode %}

### Parameters

| Name: type          | Description                                                                                             |
| ------------------- | ------------------------------------------------------------------------------------------------------- |
| `value: any`        | The **value** of any type to test against the instance of [`Wrapper`](../../wrapper.md).                |
| `opening?: Opening` | Optional **opening** chars of a generic type variable `Opening` to check if the given `value` contains. |
| `closing?: Closing` | Optional **closing** chars of a generic type variable `Closing` to check if the given `value` contains. |
| `text?: Text`       | An optional **text** of generic type variable `Text` to check if the given `value` contains.            |

### Returns

The **return value** is the text of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with a replaced **opening** chars by a given replacement value.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const quote = new Wrapper('[', ']', 'quote');
```
