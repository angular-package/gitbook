# unwrap()

### `Wrapper.unwrap()`

The method returns the **text** without the given `opening` and `closing` chars.

{% code title="wrapper.class.ts" %}
```typescript
public static unwrap(text: string, opening = '', closing = ''): string {
  return (
    (text = this.replaceClosing(text, closing, '')),
    (text = this.replaceOpening(text, opening, '')),
    text
  );
}
```
{% endcode %}

### Parameters

| Name: type        | Description                                                                                                                                                                          |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `text: string`    | The **text** of the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) from which given `opening` and `closing` chars are removed. |
| `opening: string` | The **opening** chars of the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) to be removed in the given `text`.                 |
| `closing: string` | The **closing** chars of the [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) to be removed in the given `text`.                 |

### Returns

The **return value** is the text of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type without the given **opening** and **closing** chars.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const quote = new Wrapper('[', ']', 'quote');
```
