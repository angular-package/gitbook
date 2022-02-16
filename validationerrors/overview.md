---
description: The `ValidationErrors` object
---

# Overview

## `ValidationErrors {}`

The `ValidationErrors` is an extension of the [`CommonErrors`](broken-reference) object that represents multiple identification numbers under which the errors of the [`ValidationError`](broken-reference) type are prepared to throw.

{% embed url="https://github.com/angular-package/error/blob/3.0.x/src/lib/validation-errors.class.ts" %}

### Methods

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>public</strong> <a href="methods/get.md"><strong>get()</strong></a>: <mark style="color:green;">ValidationError</mark>&#x3C;<mark style="color:green;">ErrorId</mark>> | <mark style="color:green;">undefined</mark><br>Returns the <a href="broken-reference"><code>ValidationError</code></a> instance of the given <a href="../getting-started/basic-concepts.md#unique-identification">unique identification</a> <a href="methods/get.md#id-errorid"><code>id</code></a> if set, otherwise <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined"><code>undefined</code></a>.</p>                              |
| <p><strong>public</strong> <a href="methods/geterrors.md"><strong>getErrors()</strong></a>: { [<mark style="color:green;">Key</mark> in <mark style="color:green;">Id</mark>]: <mark style="color:green;">ValidationError</mark>&#x3C;<mark style="color:green;">Key</mark>> | <mark style="color:green;">undefined</mark> }<br>Returns an <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object"><code>object</code></a> of set type errors, where the key is a <a href="../getting-started/basic-concepts.md#unique-identification">unique identification</a>.</p>                                                             |
| <p><strong>public</strong> <a href="v-methods/v-set.md"><strong>set()</strong></a><strong>:</strong> <mark style="color:green;">this</mark><br>Sets the <a href="broken-reference"><code>ValidationError</code></a> object with the message built from the given required <a href="v-methods/v-set.md#problem-string"><code>problem</code></a>, <a href="v-methods/v-set.md#id-errorid"><code>id</code></a>, <a href="v-methods/v-set.md#fix-string"><code>fix</code></a> on the given or stored <a href="v-methods/v-set.md#template-validationerrors.template"><code>template</code></a> under the given <a href="v-methods/v-set.md#id-errorid"><code>id</code></a>.</p> |
