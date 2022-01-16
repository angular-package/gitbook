# Wrap {}

The idea behind the `Wrap` is to have an object that creates a tag of string type, not a specific type like Html, or BBCode but any tag of a string with preserved exact type. Looking first at the Html tag we see that it consists of one character, a word, and one character. Based on the Html tag and by using the primitive wrapper objects, the `Wrap` object is going to be designed.

The `Wrap` string object constructor has two required parameters and one optional, resulting in three private(hashed) properties and [`get`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) accessors intuitively of the same names. The required parameters are required because they are a crucial part of the wrapping, and without them, there is no such thing as a wrap.

The constructor parameters names are the **opening** characters, **closing** characters, and optional **text** wrapped by them, which make up the primitive value of the `Wrap` object.&#x20;

#### Constructor's parameters

`opening:`<mark style="color:green;">`Opening`</mark>

`closing:`<mark style="color:green;">`Closing`</mark>

`text:`<mark style="color:green;">`Text`</mark>` ``= ''`

#### `Wrap` private properties

`#opening:`<mark style="color:green;">`Opening`</mark>

`#closing:`<mark style="color:green;">`Closing`</mark>

`#text?:`<mark style="color:green;">`Text`</mark>

#### Accessors

`get opening():`<mark style="color:green;">`Opening`</mark> refers to `#opening:`<mark style="color:green;">`Opening`</mark>

`get closing():`<mark style="color:green;">`Closing`</mark> refers to `#closing:`<mark style="color:green;">`Closing`</mark>

`get text():`<mark style="color:green;">`Text`</mark> refers to `#text:`<mark style="color:green;">`Text`</mark>

#### Primitive value

`${opening}${text}${closing}`

Getting the primitive value of the `Wrap` object is possible with native `valueOf()` and `toString()` methods. Because of their accessibility in any string, there is no need to add more.



Let's do some analysis to approve the chosen words of the constructor parameters.
