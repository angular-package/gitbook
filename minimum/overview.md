---
description: The `Minimum` primitive wrapper object
---

# Overview

## `Minimum {}`

The `Minimum` [primitive wrapper object](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) extended by the [`Inequality`](broken-reference) abstract primitive wrapper [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) represents the minimum [`number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) **greater** or **less** than the given.

{% embed url="https://github.com/angular-package/range/blob/main/src/lib/minimum.class.ts" %}
`minimum.class.ts`
{% endembed %}

{% embed url="https://github.com/angular-package/range/blob/main/src/lib/inequality.class.ts" %}
`Inequality.class.ts`
{% endembed %}

### Accessors

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>public get</strong> <a href="accessors/get-symbol.tostringtag.md"><strong>[Symbol.</strong><mark style="color:blue;"><strong>toStringTag</strong></mark><strong>]()</strong></a>: <strong></strong> <mark style="color:green;">string</mark><br>The <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get"><code>get</code></a> accessor, with the help of <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toStringTag"><code>toStringTag</code></a>, changes the default tag to <code>'Minimum'</code> for an instance of <a href="broken-reference"><code>Minimum</code></a>.</p> |

### Methods

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p><strong>public static</strong> <a href="methods/static-create.md#minimum.create"><strong>create()</strong></a>: <mark style="color:green;">Maximum</mark>&#x3C;<mark style="color:green;">Value</mark>><br>Creates the <a href="broken-reference"><code>Minimum</code></a> instance with the given primitive <a href="methods/static-create.md#value-value"><code>value</code></a>.</p>                                                                                                                                                                                                 |
| <p><strong>public static</strong> <a href="methods/static-isminimum.md#minimum.isminimum"><strong>isMinimum()</strong></a>: <mark style="color:green;">boolean</mark><br><mark style="color:green;"></mark>Checks the provided <a href="methods/static-isminimum.md#value-any"><code>value</code></a> of <a href="https://www.typescriptlang.org/docs/handbook/basic-types.html#any"><code>any</code></a> type whether is an instance of <a href="broken-reference"><code>Minimum</code></a> of any or the given <a href="methods/static-isminimum.md#min-value"><code>min</code></a>.</p> |
| <p><strong>public</strong> <a href="methods/valueof.md#minimum.prototype.valueof"><strong>valueOf()</strong></a>: <mark style="color:green;">Value</mark><br><mark style="color:green;"></mark>Returns the <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/valueOf">primitive value</a> of the generic type variable <a href="generic-type-variables.md#minimum-less-than-value-greater-than"><code>Value</code></a> of the specified <a href="broken-reference"><code>Minimum</code></a> object.</p>                                     |
