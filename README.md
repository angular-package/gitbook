---
description: '@angular-package/range'
---

# Introduction

## angular-package/range

The range package is based on the [primitive wrapper object](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) of the [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) and extends it with functionalities relevant to the range for determining inequality.

The simplest objects, `Greater` and `Less` indicate as the names suggest the [primitive value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/valueOf) is greater or less, and their purpose is to check whether it's greater or less than a single value, every of the given values, or some given values.

`Inequality` abstract [primitive wrapper object](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) has functionalities of both `Greater` and `Less` with the additional ability to check the [primitive value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/valueOf) whether it's between the range of the given minimum and maximum, it's between every of the given ranges, or it's between some given ranges.

All the features of the `Inequality` abstract [primitive wrapper object](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) are in the `Number` general object that extends it, and two objects to handle the range, the `Minimum` and `Maximum`, which also extend `Inequality`.

The title object `Range` is just an object consisting of the primitive wrapper objects `Minimum` and `Maximum`. Represents the range and determines the single value is in the range, every value of the given values is in the range, some given values are in the range by using `has` prefixed methods. Determines whether the single range is between the range, every of the given ranges is between the range, some given ranges are between the range.

That's all about the range package, let's see what are the benefits.
