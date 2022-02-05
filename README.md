---
cover: .gitbook/assets/type-introduction-cover.jpg
coverY: -334.65395894428144
---

# Introduction

The `type` package's purpose is to determine the type of single or multiple values and guard single values. It also contains common types that can be useful for other packages.

### Check & guard

The `check` means to determine the value of [any](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type by using dedicated functions like `'isNaN()'` , methods like `'isArray()'`, and operators `'typeof'`  `'instanceof'`. The `type` package functions for checking the values are prefixed with '**are**' '**is**' '**isNot**' word.

The `guard` means the same as a check but with an additional constrain type, and guard functions are prefixed with the '**guard**' word.

### Single and multiple

The difference between prefixed with '**is**' and '**are**' functions is, prefixed with '**is**' are used to check a single value of any type, prefixed with '**are**' are used for checking multiple values of any type against one type. Additionally, checking multiple values is determined by `every()`, `forEach()` or `some()` methods.

### Precise

To make the functions more precise, besides the use of '[typeof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof)' and '[instanceof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof)' operators, some of them use method '**`toString()`**' of the two objects '[Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function/toString)' and '[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/toString)' to detect the type.

### Result handler & payload

Each function includes an optional callback function to handle the check result and an optional payload. The payload parameter of the callback function contains additional useful properties specific to the function and can be extended by the payload parameter of the core function.
