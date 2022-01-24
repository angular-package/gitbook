# isWrapped()

### `isWrapped(opening, closing)`

The method checks whether the primitive value of the `Wrap` object has an opening and closing chars or the given opening and closing chars. The method parameter's default values are those from constructor initialization and, they are used in performed [`hasOpening()`](hasopening.md) and `hasClosing()` methods, so It's obvious how it behaves.

If the `text` parameter is an empty `string` following the reasoning of the `hasOpening()` and `hasClosing()`, the method returns `false` in any case.

```typescript
// Examples without the text.
// Return `false` because there is no text to wrap.
new Wrapper('{{{', '}}}').isWrapped();

// Return `false` because there is no text to wrap.
new Wrapper('{{{', '}}}', '').isWrapped());

// Return `false` because there is no text to wrap.
new Wrapper('', '}}}').isWrapped();

// Return `false` because there is no text to wrap.
new Wrapper('{{{', '').isWrapped();

```

Examples with the provided `text`.

```typescript
// Examples with the text.
// Returns `true`.
new Wrapper('{{{', '}}}', 'wrap me').isWrapped();

// Returns `false` because the opening chars is an empty `string`.
new Wrapper('', '}}}', 'wrap me').isWrapped();

// Returns `false` because the closing chars is an empty `string`.
new Wrapper('{{{', '', 'wrap me').isWrapped();

```

Let's provide some parameters to the method. The default value of parameters is assigned from an instance.

```typescript

// Examples with the text.
// Returns `true`.
new Wrapper('{{{', '}}}', 'wrap me').isWrapped('{{{', '}}}');

// Returns `true` because even if the `opening` is undefined, the default
// value of an instance is used.
new Wrapper('{{{', '}}}', 'wrap me').isWrapped(undefined, '}}}');

// Returns `true` because even if the `closing` is undefined, the default
// value of an instance is used.
new Wrapper('{{{', '}}}', 'wrap me').isWrapped('{{{', undefined);

```

The method parameters are different from the `Wrap` instance.

```typescript

// Returns `false` because different wrap.
new Wrapper('{{{', '}}}', 'wrap me').isWrapped('<<<', '>>>');

// Returns `false` because different wrap.
new Wrapper('{{{', '}}}', 'wrap me').isWrapped(undefined, '>>>');

// Returns `false` because different wrap.
new Wrapper('{{{', '}}}', 'wrap me').isWrapped('<<<', undefined);

```



### Conclusion

The method checks whether the `opening`, `closing`, and the `text` of the `Wrap` instance have a **minimum length** of **1**. Returns `true` when equal or above **1**, and `false` when below **1**.
