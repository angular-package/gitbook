---
description: The static methods of `Wrap` the string object.
---

# Methods

## Static

### Public

| Public                                                                                                                                                                                                                                                                  |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><a href="static/hasclosing.md">hasClosing()</a><br>Checks whether the <a href="static/hasclosing.md#text-string"><code>text</code></a> has given <a href="static/hasclosing.md#closing-string"><code>closing</code></a> chars at the <strong>end</strong>.</p>       |
| <p><a href="static/hasopening.md">hasOpening()</a><br>Checks whether the <a href="static/hasopening.md#text-string"><code>text</code></a> has given <a href="static/hasopening.md#opening-string"><code>opening</code></a> chars at the <strong>beginning</strong>.</p> |
| <p><a href="static/iswrap.md">isWrap()</a><br>The method checks whether the <code>value</code> of any type is the <a href="../overview.md"><code>Wrap</code></a> instance of any or given <code>opening</code> and <code>closing</code> chars.</p>                      |





















|                                      |                                                                                                                                                      |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| [hasClosing()](static/hasclosing.md) | Checks whether the [`text`](static/hasclosing.md#text-string) has given [`closing`](static/hasclosing.md#closing-string) chars at the **end**.       |
| [hasOpening()](static/hasopening.md) | Checks whether the [`text`](static/hasopening.md#text-string) has given [`opening`](static/hasopening.md#opening-string) chars at the **beginning**. |
| [isWrap()](static/iswrap.md)         | The method checks whether the `value` of any type is the [`Wrap`](../overview.md) instance of any or given `opening` and `closing` chars.            |

## Instance

### Public

|                                                  |                                                                                                                                                                                                                                                                                        |
| ------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [getClosing()](instance/getclosing.md)           | Gets the [closing](../../library/basic-concepts.md#closing) chars of the wrap by returning the [`#closing`](../properties/#closing-closing) property of a specified object.                                                                                                            |
| [getOpening()](instance/getopening.md)           | Gets the [opening](../../library/basic-concepts.md#opening) chars of the wrap by returning the [`#opening`](../properties/#opening-opening) property of a specified object.                                                                                                            |
| [getText()](instance/gettext.md)                 | Gets the text of the wrap by returning the [`#text`](../properties/#text-text) property of a specified object, without the [opening](../accessors/#wrap.prototype.opening) and [closing](../accessors/#wrap.prototype.closing) chars of the [`Wrap`](../overview.md).                  |
| [hasClosing()](instance/hasclosing.md)           | Checks whether the [primitive value](instance/valueof.md) of a specified object has the [`closing`](../accessors/closing.md) chars or given [`closing`](instance/hasclosing.md#closing-string) chars.                                                                                  |
| [hasOpening()](instance/hasopening.md)           | Checks whether the primitive value of a specified object has the [opening](../accessors/#wrap.prototype.opening) chars or given opening chars. An empty `string` indicates [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/undefined). |
| [hasText()](instance/hastext.md)                 | The method checks whether the [text](../accessors/#wrap.prototype.text) of a specified [`Wrap`](../overview.md) object is defined, which means it's a `string` of at least one char and optionally equal to the given `text`.                                                          |
| [isWrapped()](instance/iswrapped.md)             | The method checks whether the primitive value of the specified object is wrapped by the [opening](../accessors/#wrap.prototype.opening) and [closing](../accessors/#wrap.prototype.closing) chars of an instance or given opening and closing chars.                                   |
| [★ replaceClosing()](instance/replaceclosing.md) | Returns the primitive value with **replaced** **closing** chars.                                                                                                                                                                                                                       |
| [★ replaceOpening()](instance/replaceopening.md) | Returns the primitive value with **replaced** **opening** chars.                                                                                                                                                                                                                       |
| [★ replaceText()](instance/replacetext.md)       | Returns the primitive value with replaced [`text`](../accessors/text.md).                                                                                                                                                                                                              |
| [toString()](instance/tostring.md)               | Gets the [wrap](../../library/basic-concepts.md#wrap), the primitive value of a specified [`Wrap`](../overview.md) object.                                                                                                                                                             |
| [valueOf()](instance/valueof.md)                 | Returns the [wrap](../../library/basic-concepts.md#wrap), primitive value of a specified [`Wrap`](../overview.md) object.                                                                                                                                                              |
