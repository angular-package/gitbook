---
description: The `Errors` object methods
---

# Methods

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>public <a href="set.md"><strong>set(): </strong><mark style="color:green;"><strong>this</strong></mark></a><br>Sets the <a href="broken-reference"><code>Error</code></a> object with the message built from the given required <a href="set.md#problem-string"><code>problem</code></a>, <a href="set.md#id-errorid"><code>id</code></a>, <a href="set.md#fix-string"><code>fix</code></a> on the given or stored <a href="set.md#template-errors.template"><code>template</code></a> under the given <a href="set.md#id-errorid"><code>id</code></a>.</p>                          |
| <p>public <a href="toobject.md"><strong>toObject(): { [</strong><mark style="color:green;"><strong>Key</strong></mark><strong> in </strong><mark style="color:green;"><strong>Id</strong></mark><strong>]: </strong><mark style="color:green;"><strong>Error</strong></mark><strong>&#x3C;</strong><mark style="color:green;"><strong>Id</strong></mark><strong>> }</strong></a><br>The method returns the <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON">JSON</a> object of set errors, where the key is a unique identification.</p> |