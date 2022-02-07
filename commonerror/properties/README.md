# Properties

## Static

### Public

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>public static <a href="static-template.md"><strong>template: </strong><mark style="color:green;"><strong>string</strong></mark></a><br>A template of the error message of <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String"><code>string</code></a> type with the replaceable <a href="../v-constructor.md#problem"><code>{problem}</code></a>, <a href="../v-constructor.md#fix"><code>{fix}</code></a> and optional <a href="static-template.md#id"><code>{id}</code></a>, <a href="static-template.md#max"><code>{max}</code></a>, <a href="static-template.md#min"><code>{min}</code></a>, <a href="static-template.md#type"><code>{type}</code></a> tags.</p> |

## Instance

### Private

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p><strong></strong><a href="fix.md"><strong>#fix: </strong><mark style="color:green;"><strong>string</strong></mark></a><br>A privately stored possible solution to the described <a href="../../getting-started/basic-concepts.md#problem">problem</a> of a <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String"><code>string</code></a> type.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| <p><strong></strong><a href="id.md"><strong>#id?: </strong><mark style="color:green;"><strong>Id</strong></mark></a><br>A privately stored unique <a href="../../getting-started/basic-concepts.md#identification">identification</a> to the described <a href="../../getting-started/basic-concepts.md#problem">problem</a> of generic type variable <a href="../generic-type-variables.md#wrap-opening"><code>Id</code></a>.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| <p><strong></strong><a href="problem.md"><strong>#problem: </strong><mark style="color:green;"><strong>string</strong></mark></a><br>A privately stored <a href="../../getting-started/basic-concepts.md#problem">problem</a> of a <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String"><code>string</code></a> type.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| <p><strong></strong><a href="template.md"><strong>#template: </strong><mark style="color:green;"><strong>string</strong></mark></a><br>A <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String">string-type</a> privately stored <a href="../../getting-started/basic-concepts.md#template">template</a> of the error <a href="../../getting-started/basic-concepts.md#message">message</a> that contains replaceable required <a href="../v-constructor.md#fix"><code>{fix}</code></a>, <a href="../v-constructor.md#problem"><code>{problem}</code></a> and optional <a href="../v-constructor.md#id"><code>{id}</code></a>, <a href="../v-constructor.md#max"><code>{max}</code></a>, <a href="../v-constructor.md#min"><code>{min}</code></a>, <a href="../v-constructor.md#type"><code>{type}</code></a> tags.</p> |