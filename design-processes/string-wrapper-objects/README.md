# String Wrapper Objects

This section covers a small part of the designing process. Determines how to properly combine some definitions with the usage and naming the methods in objects.

### Purpose

The purpose is to achieve [**intuitiveness**](../../definitions/intuitiveness-noun.md), [**logic**](../../definitions/logic-noun.md), [**cohesiveness**](../../definitions/cohesiveness-noun.md), [**minimalism**](../../definitions/minimalism-noun.md), [**immutability**](../../definitions/immutable-adjective.md), and [**consistency**](../../definitions/consistency-noun.md) **** in the final form of the objects. So, the question is, what do these words mean in object design, how to apply them properly, and why exactly these words? The following pages bring some answers.

### Immutability

The first decision is to use [primitive wrapper objects](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript) because the [immutable](../../definitions/immutable-adjective.md) nature(out of the box) of their primitive value results in partial **immutability** achievement and use them as [functional](../../definitions/functional-adjective.md) types.

There is a need to understand how methods are **being used** and **may** be used, especially in [primitive wrapper objects](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript).&#x20;
