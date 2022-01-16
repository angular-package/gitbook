# String Wrapper Objects

## The basics

1. The object name **must** be [**intuitive**](../definitions/intuitive-adjective.md).
2. The object **functionalities** must be [**intuitive**](../definitions/intuitive-adjective.md) and **reflect** its **name**.
3. The object **should** contain only **crucial** [**functionalities**](../definitions/functionality-noun.md) to achieve **ease**-**extensibility**.
4. **Method names** **must** be [**consistent**](../definitions/consistent-adjective.md) and [**intuitive**](../definitions/intuitive-adjective.md).

## String Wrapper Object

### The primitive value

1. A **primitive** value is **divided** into private properties of **generic type variables,** which are **part** of it.&#x20;
2. Constructor **parameters** types are **generic type variables** to **preserve** the **exact** **type.**
3. A **primitive** value type is **built** of generic type variables on the template literal, which results in the **exact return type** rather than just a `string`.
4. The **part** of the **primitive value is accessible** by the use of **`get` ** accessors.
5. The **parts** of the **primitive value** are:
   1. **stored** in the **private** **hashed** **properties,**
   2. **accessible** through the `get` accessors,
   3. **immutable**, cause the use of the `get` accessor.
