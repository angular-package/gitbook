---
description: The `Greater` primitive wrapper object
---

# Overview

## `Greater {}`

The `Greater` [primitive wrapper object](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) represents the [primitive value](methods/valueof.md) of the [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type **greater** than the given.

{% embed url="https://github.com/angular-package/range/blob/main/src/lib/greater.class.ts" %}
`greater.class.ts`
{% endembed %}

### Accessors

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>public get</strong> <a href="accessors/get-symbol.tostringtag.md#symbol.tostringtag"><strong>[Symbol.</strong><mark style="color:blue;"><strong>toStringTag</strong></mark><strong>]()</strong></a>: <strong></strong> <mark style="color:green;">string</mark><br>The <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get"><code>get</code></a> accessor, with the help of <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toStringTag"><code>toStringTag</code></a>, changes the default tag to <code>'Greater'</code> for an instance of <a href="broken-reference"><code>Greater</code></a>.</p> |

### Methods

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>public static</strong> <a href="methods/static-create.md"><strong>create()</strong></a>: <mark style="color:green;">Greater</mark>&#x3C;<mark style="color:green;">Value</mark>><br>Creates the <a href="broken-reference"><code>Greater</code></a> instance with the given primitive <a href="methods/static-create.md#value-value"><code>value</code></a>.</p>                                                                                                                  |
| <p><strong>public static</strong> <a href="methods/static-isgreater.md"><strong>isGreater()</strong></a>: value is <mark style="color:green;">Greater</mark>&#x3C;<mark style="color:green;">Value</mark>><br>Checks whether the given <a href="overview.md#undefined"><code>value</code></a> is the <a href="broken-reference"><code>Greater</code></a> instance of any or given primitive value.</p>                                                                                       |
| <p><strong>public</strong> <a href="methods/than.md"><strong>than()</strong></a>: <mark style="color:green;">boolean</mark><br>Checks whether the <a href="methods/valueof.md">primitive value</a> of a specified <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object"><code>object</code></a> is greater than the given <a href="methods/than.md#value-number"><code>value</code></a>.</p>                                                     |
| <p><strong>public</strong> <a href="methods/thanevery.md"><strong>thanEvery()</strong></a>: <mark style="color:green;">boolean</mark><br>Checks whether the <a href="methods/valueof.md">primitive value</a> of a specified <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object"><code>object</code></a> is greater than <strong>every</strong> value of the given <a href="methods/thanevery.md#...values-number"><code>values</code></a>.</p> |
| <p><strong>public</strong> <a href="methods/thansome.md"><strong>thanSome()</strong></a>: <mark style="color:green;">boolean</mark><br><strong></strong>Checks whether the <a href="methods/valueof.md">primitive value</a> of a specified <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object"><code>object</code></a> is greater than <strong>some</strong> given <a href="overview.md#...values-number"><code>values</code></a>.</p>         |
| <p><strong>public</strong> <a href="methods/valueof.md"><strong>valueOf()</strong></a>: <mark style="color:green;">Value</mark><br>Returns the <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/valueOf">primitive value</a> of a specified <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object"><code>object</code></a>.</p>                                                                   |