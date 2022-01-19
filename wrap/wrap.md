# Wrap {}

The [`Wrap`](wrap.md) object represents the [immutable](https://developer.mozilla.org/en-US/docs/Glossary/Immutable) text wrapped by the [opening](../library/basic-concepts.md#opening) and [closing](../library/basic-concepts.md#closing) chars. It is designed to preserve the names of the opening, text and closing.

## Instance

### Accessors

|                                                                    |                                                                                                                                                                                                                                                                                                                                             |
| ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [closing](instance/accessors/closing.md)                           | The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the [closing](../library/basic-concepts.md#closing) of the wrap by returning the [`#closing`](instance/properties/#closing-closing) property of the specified object.                                                            |
| [opening](instance/accessors/opening.md)                           | The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the [opening](../library/basic-concepts.md#opening) of the wrap by returning the [`#opening`](instance/properties/#opening-opening) property of the specified object.                                                            |
| [text](instance/accessors/text.md)                                 | The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the text of the [`Wrap`](wrap.md) by returning the [`#text`](instance/properties/#text-text) property of a specified object.                                                                                                     |
| [\[Symbol.toStringTag\]](instance/accessors/symbol.tostringtag.md) | The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor, with the help of [`toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag) of Symbol, changes the default object tag to `wrap` for an instance of the [`Wrap`](wrap.md). |



### Properties

|                                            |                                                                                                                                 |
| ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------- |
| [#closing](instance/properties/closing.md) | Private property of the closing chars of a generic type variable [`Closing`](generic-type-variables.md#wrap-closing).           |
| [#opening](instance/properties/opening.md) | Private property of the opening chars of a generic type variable [`Opening`](generic-type-variables.md#wrap-opening).           |
| [#text](instance/properties/text.md)       | Private property of text of a generic type variable [`Text`](generic-type-variables.md#wrap-less-than...-text-...greater-than). |



### Methods

|                                                        |                                                                                                                                                                                                                                                                                              |
| ------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [getClosing()](instance/methods/getclosing.md)         | Gets the [closing](../library/basic-concepts.md#closing) chars of the wrap by returning the [`#closing`](instance/properties/#closing-closing) property of a specified object.                                                                                                               |
| [getOpening()](instance/methods/getopening.md)         | Gets the [opening](../library/basic-concepts.md#opening) chars of the wrap by returning the [`#opening`](instance/properties/#opening-opening) property of a specified object.                                                                                                               |
| [getText()](instance/methods/gettext.md)               | Gets the text of the wrap by returning the [`#text`](instance/properties/#text-text) property of a specified object, without the [opening](instance/accessors/#wrap.prototype.opening) and [closing](instance/accessors/#wrap.prototype.closing) chars of the [`Wrap`](wrap.md).             |
| [hasClosing()](instance/methods/hasclosing.md)         | Checks whether the primitive value of a specified object has the [closing](instance/accessors/#wrap.prototype.closing) chars or given closing chars. An empty `string` indicates [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined). |
| [hasOpening()](instance/methods/hasopening.md)         | Checks whether the primitive value of a specified object has the [opening](instance/accessors/#wrap.prototype.opening) chars or given opening chars. An empty `string` indicates [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined). |
| [hasText()](instance/methods/hastext.md)               | The method checks whether the [text](instance/accessors/#wrap.prototype.text) of a specified [`Wrap`](wrap.md) object is defined, which means it's a `string` of at least one char and optionally equal to the given `text`.                                                                 |
| [isWrapped()](instance/methods/iswrapped.md)           | The method checks whether the primitive value of the specified object is wrapped by the [opening](instance/accessors/#wrap.prototype.opening) and [closing](instance/accessors/#wrap.prototype.closing) chars of an instance or given opening and closing chars.                             |
| [replaceClosing()](instance/methods/replaceclosing.md) | Returns the primitive value with **replaced** **closing** chars.                                                                                                                                                                                                                             |
| [replaceOpening()](instance/methods/replaceopening.md) | Returns the primitive value with **replaced** **opening** chars.                                                                                                                                                                                                                             |
| [replaceText()](instance/methods/replacetext.md)       | Returns the primitive value with replaced [`text`](instance/accessors/text.md).                                                                                                                                                                                                              |
| [toString()](instance/methods/tostring.md)             | Gets the [wrap](../library/basic-concepts.md#wrap), the primitive value of a specified [`Wrap`](wrap.md) object.                                                                                                                                                                             |
| [valueOf()](instance/methods/valueof.md)               | Returns the [wrap](../library/basic-concepts.md#wrap), primitive value of a specified [`Wrap`](wrap.md) object.                                                                                                                                                                              |



## Static

### Methods

|                                              |                                                                                                                                    |
| -------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| [hasClosing()](static/methods/hasclosing.md) | Checks whether the `text` has given `closing` chars at the **end**.                                                                |
| [hasOpening()](static/methods/hasopening.md) | Checks whether the `text` has `opening` chars at the **beginning**.                                                                |
| [isWrap()](static/methods/iswrap.md)         | The method checks whether the `value` of any type is the [`Wrap`](wrap.md) instance of any or given `opening` and `closing` chars. |
