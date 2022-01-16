# String Wrapper Object

Under the hood of some packages are [primitive wrapper objects](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript), and below is a list containing some **pros** of using them and of important design benefits.

* ****[**Immutable**](https://developer.mozilla.org/en-US/docs/Glossary/Immutable) primitive value of [primitive wrapper objects](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript).
* A [**primitive**](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) value is divided into private properties of [generic type variables](https://www.typescriptlang.org/docs/handbook/2/generics.html).&#x20;
* A [**primitive**](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) value type is built of generic type variables on the [template literal](https://www.typescriptlang.org/docs/handbook/2/template-literal-types.html), which results in the **exact return type** rather than just a `string`.
* The **ability** to get part of the primitive value of the exact return type.
* Specific functionality objects with generic type variables(which preserves exact type) act as **precise** types.
* The most **important** functionalities for a **specific** name.
* General and [**intuitive**](broken-reference) object names.

All this above is in a **minimal**, **simple** to use, and **ease-extendable** form of objects.

<details>

<summary>Immutability</summary>

****[**Immutable**](https://developer.mozilla.org/en-US/docs/Glossary/Immutable) primitive value of [primitive wrapper objects](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript).

Some methods return converted primitive value to a form of an [immutable](https://developer.mozilla.org/en-US/docs/Glossary/Immutable) object or array.

Use the [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessors to return parts of the [primitive](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) value of a specified object.

</details>

<details>

<summary>Partial primitive value with the exact return type</summary>

A [**primitive**](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) value is divided into private properties of [generic type variables](https://www.typescriptlang.org/docs/handbook/2/generics.html). &#x20;

A [**primitive**](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) value type is built of generic type variables on the [template literal](https://www.typescriptlang.org/docs/handbook/2/template-literal-types.html), which results in the **exact return type** rather than just a `string`.

The **ability** to get part of the primitive value of the exact return type.

</details>

<details>

<summary>Object as types</summary>

Specific in functionality objects with generic type variables(which preserves type), act as **precise** types.

Objects have changed a [`Symbol.toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag) to **unique immutable** names.

Type of the objects can be detected by the [`Object.prototype.toString.call()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function/call). because of its **uniqueness** and **immutability**.&#x20;

There is `typeOf()` function of `angular-package/type` to detect these objects type.

</details>

<details>

<summary>Functionality <strong>follows</strong> the type</summary>

The most **important** functionalities, dedicated to a **specific** name.

Objects have functionalities that use their parts of [immutable](https://developer.mozilla.org/en-US/docs/Glossary/Immutable) primitive values.

</details>

<details>

<summary>Intuitiveness</summary>

General and [**intuitive**](broken-reference) object names.

[Intuitive](broken-reference) names of generic type variables.

[Intuitive](broken-reference) accessor and property names.

[Intuitive](broken-reference) method names.

</details>

<details>

<summary>Minimalism and simplicity</summary>

**Minimal**, **simple** to use and an **ease-extendable** objects.

</details>
