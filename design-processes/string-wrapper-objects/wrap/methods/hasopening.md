# hasOpening()

### `hasOpening(opening?: string);`

The method checks whether the primitive value of the `Wrap` object has an `opening` or a given `opening`. The question is, what does it mean the `Wrap` object has an `opening`?

```typescript
public hasOpening(opening?: string): boolean {
  return isStringType(this.text)
    ? isStringType(opening)
      ? isStringLength(opening, { min: 1 }) &&
        this.toString().slice(0, opening.length) === opening
      : isStringLength(this.opening, { min: 1 }) &&
        this.toString().slice(0, this.opening.length) === this.opening
    : false;
}
```



### Meaning

**Intuitively**, it should mean, if the `opening` parameter was not defined in the constructor, it causes the `get` accessor `opening` to be `undefined`, but it's **not** working this way.

The **existence** of the `hasOpening()` method seems to make **no sense** because the `opening` and `closing` parameters are **required**. There is also **no sense** in setting the `opening` and `closing` parameters to **optional** because the `Wrap` object's functionality is to wrap the `text` with them on initialize or by a method. Even if they are not optional they can be set as an empty `string`, and what's more, the `String` object performs conversion to a [`primitive string`](https://developer.mozilla.org/en-US/docs/Glossary/String).

It seems a good solution is to treat an empty `string` as `undefined`. The object's functionality is extended with wrapping by the `opening`, `closing`, or neither. However, the main functionality to wrap the `text` is ambiguous because wrap consists of the opening and closing characters and intuitively can wrap the text only with both.&#x20;

If **both** the given `opening` and `closing` characters are **empty strings**, the text is **not wrapped**. In other words, it is **wrapped** using **empty strings**.

The **definition** of '**Wrapped**' should be: the `text` is wrapped when the `opening` and `closing` characters wrap around the given, not empty `text`.&#x20;

```typescript
// The method checks whether the wrapper has opening.
new Wrapper(
    '[', // Opening
    ']'  // Closing
).hasOpening(); // Returns true.

// Returns true unless an empty string is treated like false.
new Wrapper('', ']').hasOpening(); // Should be false.

```

What's left to be discussed is the method's `opening` **optional** parameter, and it's used only to compare with the opening given in the constructor. One thing is in mind that the generic type variable indicates the exact type of the provided `opening` parameter, causing the method's existence useless. Setting the variable as a `string` makes it meaningful.



### Intuitiveness and consistency

The method name indicates the object has an opening, so it's intuitive even with the provided parameter, and its functionality is cohesive to the method's name. The verb **`has`** is a prefix in the method name indicating what the primitive value contains.



### Conclusion

The empty `string` of the `opening` parameter in the constructor means the object has not the `opening`.

The method checks whether the `opening` of the `Wrap` instance has a **minimum length** of **1**. Returns `true` when equal or above **1**, and `false` when below **1**.

The same applies to the `hasClosing()` method, so it's useless to examine this case, and as the following method, I chose the `isWrapped()`, which uses `hasOpening()` and `hasClosing()`.
