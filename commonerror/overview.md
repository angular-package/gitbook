---
cover: ../.gitbook/assets/error-common-cover.jpg
coverY: 561.625366568915
---

# Overview

## CommonError {}

​The `CommonError` abstract object to throw an identified error with a solution to the described problem.



## Static

### Properties

|                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>template</strong><br>A template of the error message of <code>string</code> type with the replaceable <code>{problem}</code>, <code>{fix}</code> and optional <code>{id}</code> words.</p> |

### Methods

#### Protected

|                                                                                                                                                                                                                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p><strong>defineMessage()</strong><br>The static "tag" method builds from the given <code>values</code> the error message of a string type on the template.</p>                                                                                                         |
| <p><strong>isError()</strong><br><strong></strong>Checks whether the value of any type is an instance of <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error"><code>Error</code></a> of any or the given identification.</p> |

## Instance

### Accessors

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong></strong><a href="accessors/fix.md"><strong>fix: </strong><mark style="color:green;"><strong>string</strong></mark></a><br>The <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get"><code>get</code></a> accessor obtains a possible solution to the described problem by returning the <a href="properties/fix.md"><code>#fix</code></a> property of a specified object.</p>                                                                                                                                                                              |
| <p><strong></strong><a href="accessors/id.md"><strong>id: </strong><mark style="color:green;"><strong>Id</strong></mark><strong> | </strong><mark style="color:green;"><strong>undefined</strong></mark></a><br>The <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get"><code>get</code></a> accessor gets the error identification by returning the <a href="properties/id.md"><code>#id</code></a> property of a specified object.</p>                                                                                                                             |
| <p><strong></strong><a href="accessors/message.md"><strong>message: </strong><mark style="color:green;"><strong>string</strong></mark></a><br>The <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get"><code>get</code></a> accessor gets the error message by returning the parent <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/message"><code>message</code></a> property of <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error"><code>Error</code></a> object.</p> |
| <p><strong></strong><a href="accessors/problem.md"><strong>problem: </strong><mark style="color:green;"><strong>string</strong></mark></a><br>The <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get"><code>get</code></a> accessor gets the problem by returning the <a href="properties/problem.md"><code>#problem</code></a> property of a specified object.</p>                                                                                                                                                                                                  |
| <p><strong></strong><a href="accessors/template.md"><strong>template: </strong><mark style="color:green;"><strong>string</strong></mark></a><br>The <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get"><code>get</code></a> accessor gets the template of the error message by returning the <a href="properties/template.md"><code>#template</code></a> property of a specified object.</p>                                                                                                                                                                        |

### Properties

|                                                                                                                                                                                                                                                                                                                                                                                                    |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong></strong><a href="properties/fix.md"><strong>#fix: </strong><mark style="color:green;"><strong>string</strong></mark></a><br>A privately stored possible solution to the described problem of a <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String"><code>string</code></a> type.</p>                                                     |
| <p><strong></strong><a href="properties/id.md"><strong>#id?: </strong><mark style="color:green;"><strong>Id</strong></mark></a><br>A privately stored unique identification to the described problem of generic type variable <code>Id</code>.</p>                                                                                                                                                 |
| <p><strong></strong><a href="properties/problem.md"><strong>#problem: </strong><mark style="color:green;"><strong>string</strong></mark></a><br>A privately stored problem of a <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String"><code>string</code></a> type.</p>                                                                                |
| <p><strong></strong><a href="properties/template.md"><strong>#template: </strong><mark style="color:green;"><strong>string</strong></mark></a><br>A string-type privately stored template of the error message that contains replaceable required <code>{fix}</code>, <code>{problem}</code> and optional <code>{id}</code>, <code>{max}</code>, <code>{min}</code>, <code>{type}</code> tags.</p> |
