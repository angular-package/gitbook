# Explanation

### Partial primitive value with the exact return type

This example explains what **partial primitive value** and the **exact return type** means in the [`Wrap`](broken-reference) `string` object.

```typescript
// Example usage.
import { Wrap } from '@angular-package/text';

// Define tag [quote].
const quoteTag = new Wrap(
  // quoteTag.opening;
  `[`,
  // quoteTag.closing;
  `]`,
  // quoteTag.content;
  'quote'
);

// The opening is of a generic type variable Opening in this case it's [.
quoteTag.opening;

// The closing is of a generic type variable Closing in this case it's ].
quoteTag.closing;

// The content is of a generic type variable Content in this case it's quote.
quoteTag.content;

```

To create primitive value of [`Wrap`](broken-reference) object there is the need to provide three parameters in order `opening`, `closing`, and optional `content`. They are stored in separate private properties which are accessible with the help of accessors, and because of this, access to **parts of the primitive value** is achieved. More, each parameter is of a generic type variable that detects the type of given value, and because of this, the **exact return type** of **primitive value** and its **parts** is achieved.

#### Immutability

All the parts that make up the primitive value of the [`Wrap`](broken-reference) object are **immutable** because they are accessible only by the `get` accessors. There is no possibility to change any part of the primitive value of the `quoteTag` object and any try to change e.g. `opening` results in the error message "_Cannot assign to 'opening' because it is a read-only property_".&#x20;

```typescript

// Cannot assign to 'opening' because it is a read-only property
// and the opening is of a generic type variable Opening in this case it's `[`.
quoteTag.opening = ; 

```



### Object as types

There is possibility to check whether the object is the `wrapper` with the help of `typeOf()` function. The name of `bbCodeWrapper` object cannot be changed in the example below.

```typescript
// Example usage.
import { Wrapper } from '@angular-package/text';
import { typeOf } from '@angular-package/type';

class CustomWrap {
  bbCode: Wrapper<`[`, `]`> = new Wrapper(`[`, `]`);
  html: Wrapper<'<', '>'> = new Wrapper(`<`, `>`);
}

// Returns [quote] of type "[quote]".
new CustomWrap().bbCode.wrap('quote');

// Returns <span> of type "<span>".
new CustomWrap().html.wrap('span');

// Checks the object type. Returns 'wrapper'.
const bbCodeWrapper = new Wrapper('[', ']');

// Returns 'wrapper'.
typeOf(bbCodeWrapper);

// Symbol.toStringTag is immutable. Can't be changed.
// Uncaught TypeError: Cannot set property Symbol(Symbol.toStringTag) of [object Object] which has only a getter
Object.assign(bbCodeWrapper, {
  [Symbol.toStringTag]: 'custom'
});

```

