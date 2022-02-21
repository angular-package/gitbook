# ❤ Benefits

### Primitive wrapper object of Number

Some objects are based on [primitive wrapper objects](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript), and below is a list containing some **pros** of using them and important design benefits.

<details>

<summary>Immutability</summary>

<mark style="color:green;">**✓**</mark> [**Immutable**](https://developer.mozilla.org/en-US/docs/Glossary/Immutable) primitive value of [primitive wrapper objects](https://developer.mozilla.org/en-US/docs/Glossary/Primitive#primitive\_wrapper\_objects\_in\_javascript).

</details>

<details>

<summary>The exact type</summary>

<mark style="color:green;">**✓**</mark> Specific functionality objects with generic type variables(which preserves exact type) act as **precise** types.

</details>

<details>

<summary>Object as types</summary>

<mark style="color:green;">**✓**</mark> Specific in functionality objects with generic type variables(which preserves type), act as **precise** types.

<mark style="color:green;">**✓**</mark> Objects have the [`Symbol.toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag) changed to **unique immutable** names.

<mark style="color:green;">**✓**</mark> Type of the objects can be determined by the [`Object.prototype.toString.call()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function/call). because of its **uniqueness** and **immutability**.&#x20;

<mark style="color:green;">**✓**</mark> There is prepared function `typeOf()` function of `@angular-package/type` to determine these objects type.

</details>

<details>

<summary>Functionality <strong>follows</strong> the type</summary>

<mark style="color:green;">**✓**</mark> The most **important** functionalities for a **specific** name.

<mark style="color:green;">**✓**</mark> Objects have functionalities that use primitive values.

</details>

<details>

<summary>Intuitiveness</summary>

<mark style="color:green;">**✓**</mark> General and [**intuitive**](general-concepts.md#intuitive) object names.

<mark style="color:green;">**✓**</mark> [Intuitive](general-concepts.md#intuitive) names of generic type variables.

<mark style="color:green;">**✓**</mark> [Intuitive](general-concepts.md#intuitive) accessor and property names.

<mark style="color:green;">**✓**</mark> [Intuitive](general-concepts.md#intuitive) method names.

</details>

<details>

<summary>Minimalism and simplicity</summary>

<mark style="color:green;">**✓**</mark>** Minimal**, **simple** to use and an **ease-extendable** objects.

</details>

### Functionality

<details>

<summary>Greater</summary>

<mark style="color:green;">**✓**</mark> Checks whether the primitive value is **greater** than the given value.

<mark style="color:green;">**✓**</mark> Checks whether the primitive value is **greater** than every of the given values.

<mark style="color:green;">**✓**</mark> Checks whether the primitive value is **greater** than some given values.

</details>

<details>

<summary>Less</summary>

<mark style="color:green;">**✓**</mark> Checks whether the primitive value is **less** than the given value.

<mark style="color:green;">**✓**</mark> Checks whether the primitive value is **less** than every of the given values.

<mark style="color:green;">**✓**</mark> Checks whether the primitive value is **less** than some given values.

</details>

<details>

<summary>Inequality</summary>

<mark style="color:green;">**✓**</mark> Functionality of both the `Greater` and `Less` objects.

<mark style="color:green;">**✓**</mark> Checks the primitive value whether it is **between** the given range of the minimum and maximum.

<mark style="color:green;">**✓**</mark> Checks the primitive value whether it is **between** every value of the given ranges.

<mark style="color:green;">**✓**</mark> Checks the primitive value whether it is **between** some given values.

</details>

<details>

<summary>Maximum</summary>

<mark style="color:green;">**✓**</mark> Functionality of the `Inequality` abstract object.

<mark style="color:green;">**✓**</mark> Indicates the **maximum** value.

</details>

<details>

<summary>Minimum</summary>

<mark style="color:green;">**✓**</mark> Functionality of the `Inequality` abstract object.

<mark style="color:green;">**✓**</mark> Indicates the **minimum** value.

</details>

<details>

<summary>Range</summary>

<mark style="color:green;">**✓**</mark> Indicates the range of **minimum and maximum**.

<mark style="color:green;">**✓**</mark> Checks whether range of the given `min` and `max` is between the range of a specified `Range` object.

<mark style="color:green;">**✓**</mark> Checks whether the range of a specified `Range` object is between every range of the given `ranges`.

<mark style="color:green;">**✓**</mark> Checks whether the range of a specified `Range` object is between some given `ranges`.

</details>
