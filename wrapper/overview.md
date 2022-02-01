# Overview

## Wrapper {}

The [`Wrapper`](https://github.com/angular-package/wrapper/blob/main/src/lib/wrapper.class.ts) is an extension of the [`Wrap`](broken-reference) object, which means it represents the [immutable](https://developer.mozilla.org/en-US/docs/Glossary/Immutable) wrap of the [opening](../library/basic-concepts.md#opening) and [closing](../library/basic-concepts.md#closing) with the additional main ability to use it to wrap strings.&#x20;

{% embed url="https://github.com/angular-package/wrapper/blob/main/src/lib/wrapper.class.ts" %}

## Instance

### Accessors

|                                                                                                                                                |                                                                                                                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ​[\[Symbol.toStringTag\]](https://app.gitbook.com/s/fKPxHpkGbNljEvVlRVgz/c/JULYvW5NSbPwI2RD5MLX/wrapper/instance-accessors#symbol.tostringtag) | The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor, with the help of `toStringTag`, changes the default tag to `'wrapper'` in the [`Wrapper`](broken-reference) instance. |



### Methods

|                                                                |                                                                                                                                                                                                                                                                                                |
| -------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [isClosingIn()](instance/methods/isclosingin.md)               | Determines whether the provided `text` has the [`closing`](../wrap/accessors/#wrap.prototype.closing) chars of the specified [`Wrapper`](overview.md) object at the **end**.                                                                                                                   |
| [isOpeningIn()](instance/methods/isopeningin.md)               | Checks whether the provided `text` has the [`opening`](../wrap/accessors/#wrap.prototype.opening) chars of a specified [`Wrapper`](overview.md) object at the **beginning**.                                                                                                                   |
| [replaceClosingIn()](instance/methods/replaceclosingin.md)     | Replaces the [`closing`](../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](overview.md) object in the given `text` with a given replacement value.                                                                                                                           |
| [replaceOpeningIn()](instance/methods/replaceopeningin.md)     | Replaces the [`opening`](../wrap/accessors/#wrap.prototype.opening) chars of the [`Wrapper`](overview.md) object in the given `text` with a given replacement value.                                                                                                                           |
| [removeWrapIn()](instance/methods/removewrapin.md)             | Returns given `text` without the [`opening`](../wrap/accessors/#wrap.prototype.opening) and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](overview.md) object.                                                                                               |
| [textReplaceClosing()](instance/methods/textreplaceclosing.md) | Replaces the [`closing`](../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](overview.md) object in the [`text`](../wrap/accessors/#wrap.prototype.text) of the [`Wrapper`](overview.md) object with the given `closing` chars.                                                |
| [textReplaceOpening()](instance/methods/textreplaceopening.md) | Replaces the [`opening`](../wrap/accessors/#wrap.prototype.opening) chars of the [`Wrapper`](overview.md) object in the [`text`](../wrap/accessors/#wrap.prototype.text) of the [`Wrapper`](overview.md) object with the given `closing` chars.                                                |
| [textUnwrap()](instance/methods/textunwrap.md)                 | The method returns the [`text`](../wrap/accessors/#wrap.prototype.text) of the [`Wrapper`](overview.md) object without its [`opening`](../wrap/accessors/#wrap.prototype.opening) and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars or the given `opening` and `closing` chars. |
| [textWrap()](instance/methods/textwrap.md)                     | The method returns the [`text`](../wrap/accessors/#wrap.prototype.text) of the [`Wrapper`](overview.md) object wrapped by the given [`opening`](../wrap/accessors/#wrap.prototype.opening) and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars.                                   |
| [toArray()](instance/methods/toarray.md)                       | Returns an `array` consisting of the [`opening`](../wrap/accessors/#wrap.prototype.opening) chars, [`text`](../wrap/accessors/#wrap.prototype.text), and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars.                                                                         |
| [toWrap()](instance/methods/towrap.md)                         | Returns the [`Wrap`](../wrap/overview.md) instance consists of the [`text`](../wrap/accessors/#wrap.prototype.text), [`opening`](../wrap/accessors/#wrap.prototype.opening) and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](overview.md) object.           |
| [unwrap()](instance/methods/unwrap.md)                         | Returns the [`text`](../wrap/accessors/#wrap.prototype.text) without the [`opening`](../wrap/accessors/#wrap.prototype.opening) and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars.                                                                                              |
| [unwrapText()](instance/methods/unwraptext.md)                 | The method returns the primitive value of a specified `Wrapper` object with text unwrapped from its [`opening`](../wrap/accessors/#wrap.prototype.opening) and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars or given `opening` and `closing` chars.                            |
| [★ wrap()](instance/methods/wrap.md)                           | The method wraps the primitive value of a specified [`Wrapper`](overview.md) object by its [`opening`](../wrap/accessors/#wrap.prototype.opening) and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars, or the given `opening` and `closing` chars.                                |
| [★ wrapOn()](instance/methods/wrapon.md)                       | Wraps given `text` with the wrap, the [`opening`](../wrap/accessors/#wrap.prototype.opening), and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](overview.md) object.                                                                                         |
| [★ wrapText()](instance/methods/wraptext.md)                   | The method returns the primitive value of the `Wrapper` object with [`text`](../wrap/accessors/#wrap.prototype.text) wrapped by given `opening` and `closing` chars.                                                                                                                           |

## Static

### Methods

|                                                      |                                                                                                                                                    |
| ---------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| [define()](static/methods/define.md)                 | Defines a new [`Wrapper`](overview.md) instance with the provided `opening`, `closing` chars, and optional `text`.                                 |
| [isWrapper()](static/methods/iswrapper.md)           | The method checks if the value of any type is an instance of the [`Wrapper`](overview.md) of any, or given `opening`, `closing` chars, and `text`. |
| [replaceClosing()](static/methods/replaceclosing.md) | Replaces the closing chars in a given `text` with a given replacement value at the end of the **text**.                                            |
| [replaceOpening()](static/methods/replaceopening.md) | Replaces the opening chars in a given `text` with a given replacement value at the beginning of the **text**.                                      |
| [unwrap()](static/methods/unwrap.md)                 | The method returns the **text** without the given `opening` and `closing` chars.                                                                   |