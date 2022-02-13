---
description: The `Errors` object
---

# Overview

## `Errors {}`

The `Errors` is an extension of the [`CommonErrors`](broken-reference) object that represents multiple identification numbers under which the errors of the [`Error`](broken-reference) type are prepared to throw.

{% embed url="https://github.com/angular-package/error/blob/3.0.x/src/lib/errors.class.ts" %}
`errors.class.ts`
{% endembed %}

### Methods

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>public</strong> <a href="methods/set.md"><strong>set()</strong></a><strong>: </strong><mark style="color:green;"><strong>this</strong></mark><br>Sets the <a href="broken-reference"><code>Error</code></a> object with the message built from the given required <a href="overview.md#problem-string"><code>problem</code></a>, <a href="overview.md#id-errorid"><code>id</code></a>, <a href="overview.md#fix-string"><code>fix</code></a> on the given or stored <a href="overview.md#template-errors.template"><code>template</code></a> under the given <a href="overview.md#id-errorid"><code>id</code></a>.</p>     |
| <p><strong>public</strong> <a href="methods/toobject.md"><strong>toObject()</strong></a><strong>: { [ </strong><mark style="color:green;"><strong>Key</strong></mark><strong> in </strong><mark style="color:green;"><strong>Id</strong></mark><strong> ]: </strong><mark style="color:green;"><strong>Error</strong></mark><strong>&#x3C;</strong><mark style="color:green;"><strong>Id</strong></mark><strong>>  }</strong> <br>The method returns the <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON">JSON</a> object of set errors, where the key is a unique identification.</p> |
