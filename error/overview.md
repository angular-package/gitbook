---
description: >-
  The `Error` object is an extension of the `CommonError` class and is thrown
  when a runtime error occurs.
---

# Overview

## Error {}

The `Error` object is an extension of the [`CommonError`](broken-reference) class and is thrown when a runtime error occurs with a [message](https://app.gitbook.com/s/23iV8ygEQUrhqw7I3D8g/\~/changes/lXvTfsmAkHoNRKsQjxlq/commonerror/accessors/get-message) built from a [solution](https://app.gitbook.com/s/23iV8ygEQUrhqw7I3D8g/\~/changes/lXvTfsmAkHoNRKsQjxlq/commonerror/accessors/get-fix) to the described [problem](https://app.gitbook.com/s/23iV8ygEQUrhqw7I3D8g/\~/changes/lXvTfsmAkHoNRKsQjxlq/commonerror/accessors/get-problem) but with additional identification, on the [template](https://app.gitbook.com/s/23iV8ygEQUrhqw7I3D8g/\~/changes/lXvTfsmAkHoNRKsQjxlq/commonerror/accessors/get-template).

{% embed url="https://github.com/angular-package/error/blob/3.0.x/src/lib/error.class.ts" %}

## Static

### Properties

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>public static <a href="../commonerror/properties/static-template.md"><strong>template: </strong><mark style="color:green;"><strong>string</strong></mark></a><br>A template of the error message of <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String"><code>string</code></a> type with the replaceable <a href="../commonerror/v-constructor.md#problem"><code>{problem}</code></a>, <a href="../commonerror/v-constructor.md#fix"><code>{fix}</code></a> and optional <a href="../commonerror/v-constructor.md#id"><code>{id}</code></a>, <a href="../commonerror/v-constructor.md#max"><code>{max}</code></a>, <a href="../commonerror/v-constructor.md#min"><code>{min}</code></a>, <a href="../commonerror/v-constructor.md#type"><code>{type}</code></a> tags.</p> |

### Methods

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>public static <a href="methods/static-define.md"><strong>define()</strong></a><br>Defines the <code>Error</code> instance with the message built of the given required <a href="methods/static-define.md#problem-string"><code>problem</code></a>, <a href="methods/static-define.md#fix-string"><code>fix</code></a> and optional <a href="methods/static-define.md#id-id"><code>id</code></a> on the <a href="methods/static-define.md#template-error.template"><code>template</code></a>.</p> |
| <p>public static <a href="methods/static-iserror.md"><strong>isError()</strong></a><strong></strong><br><strong></strong>Checks whether the <a href="overview.md#value-any"><code>value</code></a> of <a href="https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any"><code>any</code></a> type is an instance of <a href="broken-reference"><code>Error</code></a> of any or the given <a href="overview.md#id-id">identification</a>.</p>                                        |

## Instance

### Accessors

|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>public get <a href="accessors/get-name.md"><strong>name(): </strong><mark style="color:green;"><strong>string</strong></mark></a><br>The <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get"><code>get</code></a> accessor obtains a possible solution to the described <a href="../commonerror/accessors/get-problem.md">problem</a> by returning the <a href="../commonerror/properties/fix.md"><code>#fix</code></a> property of a specified object.</p>                                                                                     |
| <p>public get <a href="accessors/get-symbol.tostringtag.md"><strong>[Symbol.</strong><mark style="color:blue;"><strong>toStringTag</strong></mark><strong>](): </strong><mark style="color:green;"><strong>string</strong></mark></a><br>The <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get"><code>get</code></a> accessor gets the error <a href="../getting-started/basic-concepts.md#identification">identification</a> by returning the <a href="../commonerror/properties/id.md"><code>#id</code></a> property of a specified object.</p> |