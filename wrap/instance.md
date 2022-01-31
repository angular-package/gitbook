# Instance

## Accessors

### Public

|                                                           |                                                                                                                                                                                                                                                                                                                                           |
| --------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [closing](accessors/closing.md)                           | The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the [closing](../library/basic-concepts.md#closing) of the wrap by returning the [`#closing`](properties/#closing-closing) property of the specified object.                                                                   |
| [opening](accessors/opening.md)                           | The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the [opening](../library/basic-concepts.md#opening) of the wrap by returning the [`#opening`](properties/#opening-opening) property of the specified object.                                                                   |
| [text](accessors/text.md)                                 | The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the text of the [`Wrap`](info/) by returning the [`#text`](properties/#text-text) property of a specified object.                                                                                                              |
| [\[Symbol.toStringTag\]](accessors/symbol.tostringtag.md) | The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor, with the help of [`toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag) of Symbol, changes the default object tag to `wrap` for an instance of the [`Wrap`](info/). |

## Properties

### Private

|                                   |                                                                                                                                 |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| [#closing](properties/closing.md) | Private property of the closing chars of a generic type variable [`Closing`](generic-type-variables.md#wrap-closing).           |
| [#opening](properties/opening.md) | Private property of the opening chars of a generic type variable [`Opening`](generic-type-variables.md#wrap-opening).           |
| [#text](properties/text.md)       | Private property of text of a generic type variable [`Text`](generic-type-variables.md#wrap-less-than...-text-...greater-than). |

## Methods

### Public

|                                                        |                                                                                                                                                                                                                                                                                     |
| ------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [getClosing()](methods/instance/getclosing.md)         | Gets the [closing](../library/basic-concepts.md#closing) chars of the wrap by returning the [`#closing`](properties/#closing-closing) property of a specified object.                                                                                                               |
| [getOpening()](methods/instance/getopening.md)         | Gets the [opening](../library/basic-concepts.md#opening) chars of the wrap by returning the [`#opening`](properties/#opening-opening) property of a specified object.                                                                                                               |
| [getText()](methods/instance/gettext.md)               | Gets the text of the wrap by returning the [`#text`](properties/#text-text) property of a specified object, without the [opening](accessors/#wrap.prototype.opening) and [closing](accessors/#wrap.prototype.closing) chars of the [`Wrap`](info/).                                 |
| [hasClosing()](methods/instance/hasclosing.md)         | Checks whether the primitive value of a specified object has the [closing](accessors/#wrap.prototype.closing) chars or given closing chars. An empty `string` indicates [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined). |
| [hasOpening()](methods/instance/hasopening.md)         | Checks whether the primitive value of a specified object has the [opening](accessors/#wrap.prototype.opening) chars or given opening chars. An empty `string` indicates [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined). |
| [hasText()](methods/instance/hastext.md)               | The method checks whether the [text](accessors/#wrap.prototype.text) of a specified [`Wrap`](info/) object is defined, which means it's a `string` of at least one char and optionally equal to the given `text`.                                                                   |
| [isWrapped()](methods/instance/iswrapped.md)           | The method checks whether the primitive value of the specified object is wrapped by the [opening](accessors/#wrap.prototype.opening) and [closing](accessors/#wrap.prototype.closing) chars of an instance or given opening and closing chars.                                      |
| [replaceClosing()](methods/instance/replaceclosing.md) | Returns the primitive value with **replaced** **closing** chars.                                                                                                                                                                                                                    |
| [replaceOpening()](methods/instance/replaceopening.md) | Returns the primitive value with **replaced** **opening** chars.                                                                                                                                                                                                                    |
| [replaceText()](methods/instance/replacetext.md)       | Returns the primitive value with replaced [`text`](accessors/text.md).                                                                                                                                                                                                              |
| [toString()](methods/instance/tostring.md)             | Gets the [wrap](../library/basic-concepts.md#wrap), the primitive value of a specified [`Wrap`](info/) object.                                                                                                                                                                      |
| [valueOf()](methods/instance/valueof.md)               | Returns the [wrap](../library/basic-concepts.md#wrap), primitive value of a specified [`Wrap`](info/) object.                                                                                                                                                                       |
