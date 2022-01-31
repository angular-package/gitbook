# Wrapper() constructor

### `Wrapper()`

Creates a new [`Wrapper`](wrapper.md) instance with the **opening** and **closing** chars and optional **text**.

{% code title="wrapper.class.ts" %}
```typescript
constructor(opening: Opening, closing: Closing, text: Text = '' as Text) {
  super(opening, closing, text);
}
```
{% endcode %}

### Parameters

#### `opening: Opening`

The **opening** chars of a generic type variable [`Opening`](generic-type-variables.md#wrap-opening) placed before the given [`text`](wrapper-constructor.md#text-text).

#### `closing: Closing`

The **closing** chars of a generic type variable [`Closing`](generic-type-variables.md#wrap-closing) placed after the given [`text`](wrapper-constructor.md#text-text).

#### `text: Text`

Optional **text** of a generic type variable [`Text`](generic-type-variables.md#wrapper-less-than...-text-...greater-than) to wrap by given [`opening`](wrapper-constructor.md#opening-opening) and [`closing`](wrapper-constructor.md#closing-closing) chars.

### Returns

The **return value** is a new instance of [`Wrapper`](wrapper.md).

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

// Returns Wrapper {'{{}}'} of type Wrapper<"{{", "", "}}">
new Wrapper(`{{`, `}}`);

// Returns Wrapper {'{{variable}}'} of type Wrapper<"{{", "variable", "}}">
new Wrapper(`{{`, `}}`, 'variable');

// Returns Wrapper {'nullnull'} of typr Wrapper<any, "", any>
new Wrapper(null as any, null as any);
```
