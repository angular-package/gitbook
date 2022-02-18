---
description: '@angular-package/error'
---

# Public API

Public features that can be imported.

```typescript
import {
  // Class.
  CommonError,
  CommonErrors,
  Error,
  Errors,
  RangeError,
  RangeErrors,
  TypeError,
  TypeErrors,
  ValidationError,
  ValidationErrors
} from '@angular-package/error';
```

### `CommonError`

The [`CommonError`](broken-reference) abstract object to throw an [identified](basic-concepts.md#identification) error with a [solution](basic-concepts.md#fix) to the described [problem](basic-concepts.md#problem), additional [type](basic-concepts.md#type), and [range](basic-concepts.md#range) built on the [template](basic-concepts.md#template).

### `CommonErrors`

The [`CommonErrors`](broken-reference) object represents the storage of errors with [unique identification](basic-concepts.md#unique-identification) numbers.

### `Error`

The [`Error`](public-api.md#error) object is an extension of the [`CommonError`](broken-reference) class and is thrown when a runtime error occurs with a [message](https://app.gitbook.com/s/23iV8ygEQUrhqw7I3D8g/\~/changes/lXvTfsmAkHoNRKsQjxlq/commonerror/accessors/get-message) built from a [solution](https://app.gitbook.com/s/23iV8ygEQUrhqw7I3D8g/\~/changes/lXvTfsmAkHoNRKsQjxlq/commonerror/accessors/get-fix) to the described [problem](https://app.gitbook.com/s/23iV8ygEQUrhqw7I3D8g/\~/changes/lXvTfsmAkHoNRKsQjxlq/commonerror/accessors/get-problem) but with additional identification, on the [template](https://app.gitbook.com/s/23iV8ygEQUrhqw7I3D8g/\~/changes/lXvTfsmAkHoNRKsQjxlq/commonerror/accessors/get-template).

### `Errors`

The [`Errors`](broken-reference) is an extension of the [`CommonErrors`](broken-reference) object that represents multiple identification numbers under which the errors of the [`Error`](broken-reference) type are prepared to throw.

### `RangeError`

The [`RangeError`](broken-reference) object is an extension of the [`CommonError`](broken-reference) class and is thrown when a value is not in the set or range of allowed values with the message built from the described problem and its solution, optional explicit identification and minimum/maximum range on the given or stored template.

### `RangeErrors`

The [`RangeErrors`](broken-reference) is an extension of the [`CommonErrors`](broken-reference) object that represents multiple identification numbers under which the errors of the [`RangeError`](broken-reference) type are prepared to throw.

### `TypeError`

The [`TypeError`](broken-reference) object is an extension of the [`CommonError`](broken-reference) class and is thrown when an operation could not be performed, typically(but not exclusively) when a value is not of the expected type, with the [message](../commonerror/accessors/get-message.md) built from the described problem and its solution, optional an explicit identification and type, on the given or stored template.

### `TypeErrors`

The [`TypeErrors`](broken-reference) is an extension of the [`CommonErrors`](broken-reference) object that represents multiple identification numbers under which the errors of the [`TypeError`](broken-reference) type are prepared to throw.

### `ValidationError`

The [`ValidationError`](broken-reference) object is an extension of the [`CommonError`](broken-reference) class and is thrown when an operation could not be performed despite proper type(but not exclusively) with the [message](../commonerror/accessors/get-message.md) built from the described problem and its solution, along with additional identification on the given or stored template.

### `ValidationErrors`

The [`ValidationErrors`](broken-reference) is an extension of the [`CommonErrors`](broken-reference) object that represents multiple identification numbers under which the errors of the [`ValidationError`](broken-reference) type are prepared to throw.
