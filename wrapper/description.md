# Description

The [`Wrapper`](https://github.com/angular-package/wrapper/blob/main/src/lib/wrapper.class.ts) is an extension of the [`Wrap`](../wrap/description.md) object, which means it represents the [immutable](https://developer.mozilla.org/en-US/docs/Glossary/Immutable) wrap of the [opening](../library/basic-concepts.md#opening) and [closing](../library/basic-concepts.md#closing) with the additional main ability to use it to wrap strings.&#x20;



{% tabs %}
{% tab title="First Tab" %}

{% endtab %}

{% tab title="Second Tab" %}

{% endtab %}
{% endtabs %}

{% embed url="https://github.com/angular-package/wrapper/blob/main/src/lib/wrapper.class.ts" %}

## Instance

### Accessors

|                                                                                                                                                |                                                                                                                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ​[\[Symbol.toStringTag\]](https://app.gitbook.com/s/fKPxHpkGbNljEvVlRVgz/c/JULYvW5NSbPwI2RD5MLX/wrapper/instance-accessors#symbol.tostringtag) | The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor, with the help of `toStringTag`, changes the default tag to `'wrapper'` in the [`Wrapper`](broken-reference) instance. |



### Methods

|                                                                |                                                                                                                                                                                                                                                                                                   |
| -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [isClosingIn()](methods/instance/isclosingin.md)               | Determines whether the provided `text` has the [`closing`](../wrap/accessors/#wrap.prototype.closing) chars of the specified [`Wrapper`](description.md) object at the **end**.                                                                                                                   |
| [isOpeningIn()](methods/instance/isopeningin.md)               | Checks whether the provided `text` has the [`opening`](../wrap/accessors/#wrap.prototype.opening) chars of a specified [`Wrapper`](description.md) object at the **beginning**.                                                                                                                   |
| [replaceClosingIn()](methods/instance/replaceclosingin.md)     | Replaces the [`closing`](../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](description.md) object in the given `text` with a given replacement value.                                                                                                                           |
| [replaceOpeningIn()](methods/instance/replaceopeningin.md)     | Replaces the [`opening`](../wrap/accessors/#wrap.prototype.opening) chars of the [`Wrapper`](description.md) object in the given `text` with a given replacement value.                                                                                                                           |
| [removeWrapIn()](methods/instance/removewrapin.md)             | Returns given `text` without the [`opening`](../wrap/accessors/#wrap.prototype.opening) and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](description.md) object.                                                                                               |
| [textReplaceClosing()](methods/instance/textreplaceclosing.md) | Replaces the [`closing`](../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](description.md) object in the [`text`](../wrap/accessors/#wrap.prototype.text) of the [`Wrapper`](description.md) object with the given `closing` chars.                                             |
| [textReplaceOpening()](methods/instance/textreplaceopening.md) | Replaces the [`opening`](../wrap/accessors/#wrap.prototype.opening) chars of the [`Wrapper`](description.md) object in the [`text`](../wrap/accessors/#wrap.prototype.text) of the [`Wrapper`](description.md) object with the given `closing` chars.                                             |
| [textUnwrap()](methods/instance/textunwrap.md)                 | The method returns the [`text`](../wrap/accessors/#wrap.prototype.text) of the [`Wrapper`](description.md) object without its [`opening`](../wrap/accessors/#wrap.prototype.opening) and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars or the given `opening` and `closing` chars. |
| [textWrap()](methods/instance/textwrap.md)                     | The method returns the [`text`](../wrap/accessors/#wrap.prototype.text) of the [`Wrapper`](description.md) object wrapped by the given [`opening`](../wrap/accessors/#wrap.prototype.opening) and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars.                                   |
| [toArray()](methods/instance/toarray.md)                       | Returns an `array` consisting of the [`opening`](../wrap/accessors/#wrap.prototype.opening) chars, [`text`](../wrap/accessors/#wrap.prototype.text), and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars.                                                                            |
| [toWrap()](methods/instance/towrap.md)                         | Returns the [`Wrap`](../wrap/description.md) instance consists of the [`text`](../wrap/accessors/#wrap.prototype.text), [`opening`](../wrap/accessors/#wrap.prototype.opening) and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](description.md) object.        |
| [unwrap()](methods/instance/unwrap.md)                         | Returns the [`text`](../wrap/accessors/#wrap.prototype.text) without the [`opening`](../wrap/accessors/#wrap.prototype.opening) and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars.                                                                                                 |
| [unwrapText()](methods/instance/unwraptext.md)                 | The method returns the primitive value of a specified `Wrapper` object with text unwrapped from its [`opening`](../wrap/accessors/#wrap.prototype.opening) and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars or given `opening` and `closing` chars.                               |
| [★ wrap()](methods/instance/wrap.md)                           | The method wraps the primitive value of a specified [`Wrapper`](description.md) object by its [`opening`](../wrap/accessors/#wrap.prototype.opening) and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars, or the given `opening` and `closing` chars.                                |
| [★ wrapOn()](methods/instance/wrapon.md)                       | Wraps given `text` with the wrap, the [`opening`](../wrap/accessors/#wrap.prototype.opening), and [`closing`](../wrap/accessors/#wrap.prototype.closing) chars of the [`Wrapper`](description.md) object.                                                                                         |
| [★ wrapText()](methods/instance/wraptext.md)                   | The method returns the primitive value of the `Wrapper` object with [`text`](../wrap/accessors/#wrap.prototype.text) wrapped by given `opening` and `closing` chars.                                                                                                                              |

## Static

### Methods

|                                                      |                                                                                                                                                       |
| ---------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| [define()](methods/static/define.md)                 | Defines a new [`Wrapper`](description.md) instance with the provided `opening`, `closing` chars, and optional `text`.                                 |
| [isWrapper()](methods/static/iswrapper.md)           | The method checks if the value of any type is an instance of the [`Wrapper`](description.md) of any, or given `opening`, `closing` chars, and `text`. |
| [replaceClosing()](methods/static/replaceclosing.md) | Replaces the closing chars in a given `text` with a given replacement value at the end of the **text**.                                               |
| [replaceOpening()](methods/static/replaceopening.md) | Replaces the opening chars in a given `text` with a given replacement value at the beginning of the **text**.                                         |
| [unwrap()](methods/static/unwrap.md)                 | The method returns the **text** without the given `opening` and `closing` chars.                                                                      |
