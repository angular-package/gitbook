---
description: The `ValidationErrors` object
---

# Overview

## `ValidationErrors {}`

The `ValidationErrors` is an extension of the `CommonErrors` object that represents multiple identification numbers under which the errors of the `ValidationError` type are prepared to throw.

{% embed url="https://github.com/angular-package/error/blob/3.0.x/src/lib/validation-errors.class.ts" %}

### Methods

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>public</strong> <a href="../rangeerrors/methods/set.md"><strong>set()</strong></a><mark style="color:green;"><strong>: this</strong></mark><br>Sets the <a href="broken-reference"><code>ValidationError</code></a> object with the message built from the given required <a href="v-methods/v-set.md#problem-string"><code>problem</code></a>, <a href="v-methods/v-set.md#id-errorid"><code>id</code></a>, <a href="v-methods/v-set.md#fix-string"><code>fix</code></a> on the given or stored <a href="v-methods/v-set.md#template-rangeerrors.template"><code>template</code></a> under the given <a href="v-methods/v-set.md#id-errorid"><code>id</code></a>.</p>            |
| <p>public <a href="../rangeerrors/methods/toobject.md"><strong>toObject(): { [</strong><mark style="color:green;"><strong>Key</strong></mark><strong> in </strong><mark style="color:green;"><strong>Id</strong></mark><strong>]: </strong><mark style="color:green;"><strong>RangeError</strong></mark><strong>&#x3C;</strong><mark style="color:green;"><strong>Id</strong></mark><strong>> }</strong></a><br>The method returns the <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON">JSON</a> object of set errors, where the key is a <a href="../getting-started/basic-concepts.md#unique-identification">unique identification</a>.</p> |
