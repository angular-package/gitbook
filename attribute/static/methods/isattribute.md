# isAttribute()

### `Attribute.isAttribute()`

The method checks whether the `value` of any type is the [`Wrap`](broken-reference) instance of any or given `opening` and `closing` chars.

{% code title="attribute.class.ts" %}
```typescript
public static isAttribute<Name extends string, Value extends string>(
  value: any,
  name?: Name,
  val?: Value
): value is Attribute<Name, Value> {
  return typeof value === 'object' && value instanceof this
    ? (typeof name === 'string' ? value.name === name : true) &&
        (typeof val === 'string' ? value.value === val : true)
    : false;
}
```
{% endcode %}

| Generic type variables                                                                                                                                                                                                                                                                                                                                                                                               |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong><code>Name extends string</code></strong></p><p>A generic type variable constrained by the <a href="https://www.typescriptlang.org/docs/handbook/basic-types.html#string"><code>string</code></a>, by default of the value captured from the provided <code>opening</code> indicates the <code>Opening</code> type of the <a href="broken-reference"><code>Wrap</code></a> instance the return type.</p>  |
| <p><strong><code>Value extends string</code></strong></p><p>A generic type variable constrained by the <a href="https://www.typescriptlang.org/docs/handbook/basic-types.html#string"><code>string</code></a>, by default of the value captured from the provided <code>closing</code> indicates the <code>Closing</code> type of the <a href="broken-reference"><code>Wrap</code></a> instance via return type.</p> |

### Parameters

| Name: type    | Description                                                                                                        |
| ------------- | ------------------------------------------------------------------------------------------------------------------ |
| `value: any`  | The value of any type to test against the [`Wrap`](broken-reference) instance of any or given opening and closing. |
| `name?: Name` | Optional opening chars of a generic type variable `Opening` to check if the given `value` contains.                |
| `val?: Value` | Optional closing chars of a generic type variable `Closing` to check if the given `value` contains.                |

### Returns

| Return type                                                                                                                                                                                                                                                                                                                                  |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong><code>value is Attribute&#x3C;Name, Value></code></strong></p><p>The return type is a <code>boolean</code> indicating the <code>value</code> parameter is an instance of <a href="broken-reference"><code>Wrap</code></a> that takes a generic type variable <code>Opening</code> <code>Text</code> and <code>Closing</code>.</p> |

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type indicating whether the value is an instance of `Wrap` of any, or the given `opening`, `closing`, and `text`.

### Example usage

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

const tagWrap = new Wrap(`[`, `]`, 'quote');

// Returns true confirming the type Wrap<"[", "", "]">
Wrap.isWrap(tagWrap);

// Returns true, confirming the type Wrap<"[", "", "]">
Wrap.isWrap(tagWrap, '[', ']');

// Returns true, confirming the type Wrap<"[", "quote", "]">
Wrap.isWrap(tagWrap, '[', ']', 'quote');

// Returns true, confirming the type Wrap<"[", "", "]">
Wrap.isWrap<'[', ']'>(tagWrap, '[', ']');

// Returns false, denying the type Wrap<"[", "span", "]">
Wrap.isWrap(tagWrap, '[', ']', 'span');

// Returns false denying the value is Wrap<"(", "", ")">
Wrap.isWrap(tagWrap, '(', ')');

// Returns false denying the value is Wrap<"(", "", ")">
Wrap.isWrap<'[', ']'>(null as any);

// Returns false denying the value is Wrap<"[", "", "]">
Wrap.isWrap(null as any, '[', ']');
```

