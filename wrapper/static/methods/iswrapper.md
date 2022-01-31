# isWrapper()

### `Wrapper.isWrapper()`

The method checks if the value of any type is an instance of the [`Wrapper`](../../wrapper.md) of any, or given `opening`, `closing` chars, and `text`.

{% code title="wrapper.class.ts" %}
```typescript
public static isWrapper<
  Opening extends string,
  Closing extends string,
  Text extends string = ''
>(
  value: any,
  opening?: Opening,
  closing?: Closing,
  text?: Text
): value is Wrapper<Opening, Text, Closing> {
  return (
    typeof value === 'object' &&
    value instanceof this &&
    super.isWrap(value, opening, closing, text)
  );
}
```
{% endcode %}

| Generic type variables                                                                                                                                                                                                                                                                                                                                                                                                       | Name |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---- |
| <p><strong><code>Opening extends string</code></strong></p><p>A generic type variable constrained by the <a href="https://www.typescriptlang.org/docs/handbook/basic-types.html#string"><code>string</code></a>, by default of the value captured from the provided <code>opening</code> indicates the type of the opening in the <a href="../../wrapper.md"><code>Wrapper</code></a> via return type.</p>                   |      |
| <p><strong><code>Closing extends string</code></strong></p><p>A generic type variable constrained by the <a href="https://www.typescriptlang.org/docs/handbook/basic-types.html#string"><code>string</code></a>, by default of the value captured from the provided <code>closing</code> indicates the type of the closing in the <a href="../../wrapper.md"><code>Wrapper</code></a> via return type.</p>                   |      |
| <p><strong><code>Text extends string</code></strong><br><strong><code></code></strong>A generic type variable constrained by the <a href="https://www.typescriptlang.org/docs/handbook/basic-types.html#string"><code>string</code></a>, by default of the value captured from the provided <code>text</code> indicates the type of the text in the <a href="../../wrapper.md"><code>Wrapper</code></a> via return type.</p> |      |

### Parameters

| Name: type          | Description                                                                                             |
| ------------------- | ------------------------------------------------------------------------------------------------------- |
| `value: any`        | The **value** of any type to test against the instance of [`Wrapper`](../../wrapper.md).                |
| `opening?: Opening` | Optional **opening** chars of a generic type variable `Opening` to check if the given `value` contains. |
| `closing?: Closing` | Optional **closing** chars of a generic type variable `Closing` to check if the given `value` contains. |
| `text?: Text`       | An optional **text** of generic type variable `Text` to check if the given `value` contains.            |

#### Returns

| Return type                                                                                                                                                                                                                      |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong><code>value is Wrapper&#x3C;Opening, Text, Closing></code></strong></p><p>The return type <strong></strong> indicates the <code>value</code> is the <a href="../../wrapper.md"><code>Wrapper</code></a> instance.</p> |

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type indicating whether the value is an instance of [`Wrapper`](../../wrapper.md) of any, or the given `opening`, `closing` chars, and `text`.

### Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

const tagWrapper = new Wrapper('[', ']');

// Returns true confirming the type Wrapper<string, "", string>
Wrapper.isWrapper(tagWrapper);

// Returns true confirming the type Wrapper<"[", "", "]">
Wrapper.isWrapper<'[', ']'>(tagWrapper);

// Returns false denying the type Wrapper<"[", "", "]">
Wrapper.isWrapper<'[', ']'>(null as any);
```
