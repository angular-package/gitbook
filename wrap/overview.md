# Overview

## Wrap {}

The [`Wrap`](overview.md) object is based on the [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) object and represents the [immutable](https://developer.mozilla.org/en-US/docs/Glossary/Immutable) primitive value of the [text](../library/basic-concepts.md#wrap-content) wrapped by the [opening](../library/basic-concepts.md#opening) and [closing](../library/basic-concepts.md#closing) chars. It is designed to preserve the type names of the supplied opening, text, and closing chars by using the generic type variables.

{% embed url="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#string_primitives_and_string_objects" %}

{% embed url="https://www.typescriptlang.org/docs/handbook/2/template-literal-types.html" %}

## Instance

### Accessors

|                                                           |                                                                                                                                                                                                                                                                                                                                                 |
| --------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [closing](accessors/closing.md)                           | The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the [closing](../library/basic-concepts.md#closing) of the wrap by returning the [`#closing`](properties/closing.md) property of the specified object.                                                                               |
| [opening](accessors/opening.md)                           | The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the [opening](../library/basic-concepts.md#opening) of the wrap by returning the [`#opening`](properties/opening.md) property of the specified object.                                                                               |
| [text](accessors/text.md)                                 | The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor gets the text of the [`Wrap`](overview.md) by returning the [`#text`](properties/text.md) property of a specified object.                                                                                                                 |
| [\[Symbol.toStringTag\]](accessors/symbol.tostringtag.md) | The [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessor, with the help of [`toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag) of Symbol, changes the default object tag to `wrap` for an instance of the [`Wrap`](overview.md). |

### Properties

|                                   |                                                                                                                                 |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| [#closing](properties/closing.md) | Private property of the closing chars of a generic type variable [`Closing`](generic-type-variables.md#wrap-closing).           |
| [#opening](properties/opening.md) | Private property of the opening chars of a generic type variable [`Opening`](generic-type-variables.md#wrap-opening).           |
| [#text](properties/text.md)       | Private property of text of a generic type variable [`Text`](generic-type-variables.md#wrap-less-than...-text-...greater-than). |

### Methods

|                                                        |                                                                                                                                                                                                                                                                                                          |
| ------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [getClosing()](methods/instance/getclosing.md)         | Gets the [closing](../library/basic-concepts.md#closing) chars of the wrap by returning the [`#closing`](properties/closing.md) property of a specified object.                                                                                                                                          |
| [getOpening()](methods/instance/getopening.md)         | Gets the [opening](../library/basic-concepts.md#opening) chars of the wrap by returning the [`#opening`](properties/opening.md) property of a specified object.                                                                                                                                          |
| [getText()](methods/instance/gettext.md)               | Gets the text of the wrap by returning the [`#text`](properties/text.md) property of a specified object, without the [opening](accessors/opening.md) and [closing](accessors/closing.md) chars of the [`Wrap`](overview.md).                                                                             |
| [hasClosing()](methods/instance/hasclosing.md)         | Checks whether the [primitive value](methods/instance/valueof.md) of a specified object has the [`closing`](accessors/closing.md) chars or given [`closing`](methods/instance/hasclosing.md#closing-string) chars.                                                                                       |
| [hasOpening()](methods/instance/hasopening.md)         | Checks whether the [primitive value](methods/instance/valueof.md) of a specified object has the [`opening`](accessors/opening.md) chars or given `opening` chars.                                                                                                                                        |
| [hasText()](methods/instance/hastext.md)               | The method checks whether the [`text`](accessors/text.md) of a specified [`Wrap`](overview.md) object is defined, which means it's a [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) of at least one char and optionally equal to the given `text`. |
| [isWrapped()](methods/instance/iswrapped.md)           | The method checks whether the [primitive value](methods/instance/valueof.md) of the specified object is wrapped by the [opening](accessors/opening.md) and [closing](accessors/closing.md) chars of an instance or given `opening` and `closing` chars.                                                  |
| [replaceClosing()](methods/instance/replaceclosing.md) | Returns the [primitive value](methods/instance/valueof.md) with **replaced** [`closing`](accessors/closing.md) chars.                                                                                                                                                                                    |
| [replaceOpening()](methods/instance/replaceopening.md) | Returns the [primitive value](methods/instance/valueof.md) with **replaced** [`opening`](accessors/opening.md) chars.                                                                                                                                                                                    |
| [replaceText()](methods/instance/replacetext.md)       | Returns the [primitive value](methods/instance/valueof.md) with replaced [`text`](accessors/text.md).                                                                                                                                                                                                    |
| [toString()](methods/instance/tostring.md)             | Gets the [wrap](../library/basic-concepts.md#wrap), the primitive value of a specified [`Wrap`](overview.md) object.                                                                                                                                                                                     |
| [valueOf()](methods/instance/valueof.md)               | Returns the [wrap](../library/basic-concepts.md#wrap), [primitive value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/valueOf) of a specified [`Wrap`](overview.md) object.                                                                                  |

## Static

### Methods

|                                              |                                                                                                                                        |
| -------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| [hasClosing()](methods/static/hasclosing.md) | Checks whether the `text` has given `closing` chars at the **end**.                                                                    |
| [hasOpening()](methods/static/hasopening.md) | Checks whether the `text` has `opening` chars at the **beginning**.                                                                    |
| [isWrap()](methods/static/iswrap.md)         | The method checks whether the `value` of any type is the [`Wrap`](overview.md) instance of any or given `opening` and `closing` chars. |
