---
description: The error package basic concepts
---

# Basic concepts

### Fix

A potential solution to the described [problem](basic-concepts.md#problem).

### Message

The error message that is built from the required problem, fix and optional range, type on the template.

### Problem

The problem that causes an error to be thrown.

### Range

The minimum and maximum range that causes the [`RangeError`](broken-reference) to be or not to be thrown.

### Link

A link that refers to the potential solution of the problem.

### Template

A template for the message error with replaceable variable tags.

### Type

The type that causes the [`TypeError`](broken-reference) to be or not to be thrown.

### Unique identification

The unique identification of the error help finds a solution. It's based on a generic type variable to get the exact type.
