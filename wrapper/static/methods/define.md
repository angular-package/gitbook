# define()

### `Wrapper.define()`

Defines a new [`Wrapper`](../../wrapper.md) instance with the provided `opening`, `closing` chars, and optional `text`.

{% code title="wrapper.class.ts" %}
```typescript
public static define<
  Opening extends string,
  Closing extends string,
  Text extends string = ''
>(
  opening: Opening,
  closing: Closing,
  text?: Text
): Wrapper<Opening, Text, Closing> {
  return new this(opening, closing, text);
}
```
{% endcode %}

| Generic type variables                                                                                                                                                                                                                                                                                                                                                                                                       | Name |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---- |
| <p><strong><code>Opening extends string</code></strong></p><p>A generic type variable constrained by the <a href="https://www.typescriptlang.org/docs/handbook/basic-types.html#string"><code>string</code></a>, by default of the value captured from the provided <code>opening</code> indicates the type of the opening in the <a href="broken-reference"><code>Wrapper</code></a> via return type.</p>                   |      |
| <p><strong><code>Closing extends string</code></strong></p><p>A generic type variable constrained by the <a href="https://www.typescriptlang.org/docs/handbook/basic-types.html#string"><code>string</code></a>, by default of the value captured from the provided <code>closing</code> indicates the type of the closing in the <a href="broken-reference"><code>Wrapper</code></a> via return type.</p>                   |      |
| <p><strong><code>Text extends string</code></strong><br><strong><code></code></strong>A generic type variable constrained by the <a href="https://www.typescriptlang.org/docs/handbook/basic-types.html#string"><code>string</code></a>, by default of the value captured from the provided <code>text</code> indicates the type of the text in the <a href="broken-reference"><code>Wrapper</code></a> via return type.</p> |      |

### Parameters

| Name: type         | Description                                                                                              |
| ------------------ | -------------------------------------------------------------------------------------------------------- |
| `opening: Opening` | The **opening** chars of generic type variable `Opening` for new [`Wrapper`](../../wrapper.md) instance. |
| `closing: Closing` | The **closing** chars of generic type variable `Closing` for new [`Wrapper`](../../wrapper.md) instance. |
| `text?: Text`      | An optional **text** of generic type variable `Text` for new [`Wrapper`](../../wrapper.md) instance.     |

### Returns

The **return value** is the [`Wrapper`](../../wrapper.md) instance of given `opening`, `closing` chars, and optional `text`.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

// Returns Wrapper {'()'}
// of type Wrapper<"(", "", ")">
Wrapper.define('(', ')');

// Returns Wrapper {'!!'}
// of type Wrapper<"!", "", "!">
Wrapper.define('!', '!');

// Returns Wrapper {'"This is quoted text"'}
// of type Wrapper<"\"", "This is quoted text", "\"">
Wrapper.define('"', '"', 'This is quoted text');
```

