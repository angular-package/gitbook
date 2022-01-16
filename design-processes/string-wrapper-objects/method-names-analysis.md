# Method names analysis

{% hint style="info" %}
It is worth checking only the method name, not including the object and its functionality, because then it's possible to achieve constant intuitive method names, at first sight, indicating its meaning. The need is also to have the same parameters.
{% endhint %}

This page covers building the method names using the approaches of the page '[methods usage analysis](methods-usage-analysis.md)'. Method names consist of selected words, and among others, there are **verbs**, **prepositions**, and **nouns** in a specific **order**, where can be found [intuitiveness](../../definitions/intuitiveness-noun.md) and [functionality](../../definitions/functionality-noun.md). The methods perform actions, and the first step is to create a small list of them.

## Possible actions

There are possible actions that can be performed on an instance, and the following list contains a few general words that are used to build method name structures below.

* ~~exec~~ ([**noun**](../../definitions/noun-noun.md))
* get ([**verb**](../../definitions/verb-noun.md))\
  Indicates a direction **pick-out**.\

* has ([**verb**](../../definitions/verb-noun.md)) (Indicating possibility)\
  Indicates a direction **pick-check-out**.\

* is (a state of being [verb](../../definitions/verb-noun.md))\
  Indicates a direction **pick-check-out**.\

* replace ([**verb**](../../definitions/verb-noun.md))\
  Indicates a direction **pick-change-out**.\

* set ([**verb**](../../definitions/verb-noun.md))\
  Indicates a direction **pick-change-in**.\

* to ([**preposition**](../../definitions/preposition-noun.md))\
  Indicates a direction **pick-(change)-out**.\

* wrap ([**verb**](../../definitions/verb-noun.md) or [**noun**](../../definitions/noun-noun.md))\
  Indicates a direction **pick-change-out**.

## **Approaches**

The nine following approaches show possible name structures that clarify the method naming methodology. The method name structure is built from a few simple brackets, with the description and type, like in the following example.&#x20;

\[ action: **verb | noun** ]\[ what: **noun | verb** ]\(\[ parameter: **noun** ])

****

### **One**

{% hint style="info" %}
The method **without** **parameters** gets the **primitive value** and returns a **primitive value**.
{% endhint %}

#### **`get`**<mark style="color:orange;">`()`</mark>

\[ get: **verb** ]\()

```typescript
new Wrap('<', '>', 'span').get(); // Returns <span>
```

#### **`getPrimitive`**<mark style="color:orange;">`()`</mark>

\[ get: **verb** ]\[ Primitive: **noun** ]\()

```typescript
new Wrap('<', '>', 'span').getPrimitive(); // Returns <span>
```

#### `getWrap`<mark style="color:orange;">`()`</mark>

\[ get: **verb** ]\[ Wrap: **noun** ]\()

```typescript
new Wrap('<', '>', 'span').getWrap(); // Returns <span>
```

#### `toPrimitive`<mark style="color:orange;">`()`</mark>

\[ to: **preposition** ]\[ Primitive: **noun** ]\()

```typescript
new Wrap('<', '>', 'span').toPrimitive(); // Returns <span>
```

#### `toString`<mark style="color:orange;">`()`</mark>

\[ to: **preposition** ]\[ String: **noun** ]\()

```typescript
new Wrap('<', '>').toString(); // Returns <>
```

#### `valueOf`<mark style="color:orange;">`()`</mark>

\[ value: **noun** ]\[ Of: **preposition** ]\()

```typescript
new Wrap('<', '>').valueOf(); // Returns <>
```

#### Conclusion

The simple method names with prefixes like a **verb**, **preposition**, or even **noun** return the primitive value of a specified object.

Especially the [`valueOf()`](method-names-analysis.md#valueof) method name indicates that the **noun** `value` is like a property picked with the following action performed on it. This way of thinking where the method name first word denotes getting the property is helpful in [approach eight](method-names-analysis.md#eight) and [approach three](method-names-analysis.md#three).

* The actions assigned to this approach are **`get`** and **`to`** indicate getting the primitive value.
* The action **`get`** without the following word indicates the return of the primitive value.



### **Two**

{% hint style="info" %}
The method **without** **parameters** gets the **primitive value** and performs an action on it based on the **intuitive** method name, and **returns** the **changed primitive value**.
{% endhint %}

#### **`big`**<mark style="color:orange;">`()`</mark>

\[ big: **verb** ]\()

```typescript
new String('text').big() // Returns <big>text</big>
new Wrap('<', '>').big(); // Returns <big><></big>
```

#### `bold`<mark style="color:orange;">`()`</mark>

\[ bold: **verb** ]\()

```typescript
new String('text').bold(); // Returns <b>text</b>
new Wrap('<', '>', 'span').bold(); // Returns <b><span></b>
```

#### **Conclusion**

These methods are native methods of the [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/String) object, and their meaning is to transform the primitive value to the bold or big. No words in their names are informing about how they behave. They could have added prepositions, for example, '[**to**](../../definitions/to-preposition.md)' to get `toBig()` or `toBold()`, but are they necessary? However, these methods are denoted as deprecated.

It seems better to have a [**verb**](../../definitions/verb-noun.md) instead of a [**noun**](../../definitions/noun-noun.md) in the method name of one word because nouns are reserved names for properties or accessors.

* One of the exceptions is the '**wrap**' word cause it's a **verb** and **noun**.



### Three

{% hint style="info" %}
The method **with** **parameters** gets the **primitive value** and performs an action on it based on the **intuitive** method name with the **use** of its **parameters** and **returns** the **changed primitive value**.
{% endhint %}

#### **`replace`**<mark style="color:orange;">**`(`**</mark>**`searchValue: string, replaceValue: string`**<mark style="color:orange;">`)`</mark>

\[ replace: **verb** ]\(\[ searchValue: **noun** ], \[ replaceValue: **noun** ])

```typescript
new String('text').replace('e', 'E'); // Returns tExt
new Wrapper('<', '>', 'span').replace('a', 'A'); // Returns <spAn>
```

#### `wrap`<mark style="color:orange;">**`(`**</mark>`opening: string, closing: string`<mark style="color:orange;">`)`</mark>

\[ wrap: **verb** ]\(\[ opening: **noun** ], \[ closing: **noun** ])

```typescript
new Wrapper('<', '>', 'span').wrap('{', '}'); // Returns {<span>}
new Wrapper('', '', 'span').wrap('{', '}'); // Returns {span}
```

#### `wrapText`<mark style="color:orange;">`(`</mark>`opening: string, closing: string`<mark style="color:orange;">`)`</mark>

\[ wrap: **verb** ]\[ Text: **noun** ]\(\[ opening: **noun** ], \[ closing: **noun** ])

```typescript
new Wrapper('<', '>', 'span').wrapText('{', '}'); // Returns <{span}>
```

#### `wrapOpening`<mark style="color:orange;">`(`</mark>`opening: string, closing: string`<mark style="color:orange;">`)`</mark>

\[ wrap: **verb** ]\[ Opening: **noun** ]\(\[ opening: **noun** ], \[ closing: **noun** ])

```typescript
new Wrapper('<', '>', 'span').wrapOpening('{', '}'); // Returns {<}span>
new Wrapper('', '>', 'span').wrapOpening('{', '}'); // Returns {}span>
```

What should be returned in this method, the primitive value with changed opening or wrapped opening? The following method could be an answer.

#### `openingWrap`<mark style="color:orange;">`(`</mark>`opening: string, closing: string`<mark style="color:orange;">`)`</mark>

\[ opening: **noun** ]\[ Wrap: **verb** ]\(\[ opening: **noun** ], \[ closing: **noun** ])

```typescript
// Returns {<}span> or {<}
new Wrapper('<', '>', 'span').openingWrap('{', '}'); // Returns {<}
```

The action(**verb**, **preposition**) following the object indicates performing this action on the primitive value. The **noun** indicates getting the property to perform on it. The result of this method should be a wrapped opening `{>}`.

#### `replaceOpening`<mark style="color:orange;">`(`</mark>`opening: string`<mark style="color:orange;">`)`</mark>

\[ replace: **verb** ]\[ Opening: **noun** ]\(\[ opening: **noun** ])

```typescript
new Wrapper('<', '>', 'span').replaceOpening('{'); // Returns {span>
new Wrapper('<', '', 'span').replaceOpening('{'); // Returns {span>
new Wrapper('<', '>', 'span').replaceOpening('{{{'); // Returns {{{span>
```

#### `replaceClosing`<mark style="color:orange;">`(`</mark>`closing: string`<mark style="color:orange;">`)`</mark>

\[ replace: **verb** ]\[ Closing: **noun** ]\(\[ closing: **noun** ])

```typescript
new Wrapper('<', '>', 'span').replaceClosing('}'); // Returns <span}
new Wrapper('<', '', 'span').replaceClosing('}'); // Returns <span}
new Wrapper('<', '>', 'span').replaceClosing('}}}'); // Returns <span}}}
```

#### `replaceText`<mark style="color:orange;">`(`</mark>`text: string`<mark style="color:orange;">`)`</mark>

\[ replace: **verb** ]\[ Text: **noun** ]\(\[ text: **noun** ])

```typescript
new Wrapper('{', '}', 'span').replaceText('div'); // Returns {div}
```

**Conclusion**

* The actions assigned to this approach are **`replace`**, **`wrap`**.
* If the object is followed by a **verb** the method changes the primitive value or its parts and returns the changed primitive value.
* If the object is followed by a **noun** the method changes the primitive value part and returns it.
* Following **intuitiveness** of native method [`replace()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/replace) the `wrap` method should return the primitive value of the `Wrapper` after replacing.



### Four

{% hint style="info" %}
The method **without** **parameters** gets **part** of the **primitive value** and **returns it**.
{% endhint %}

Previous [approach three](method-names-analysis.md#three) teaches that a **noun** **after** the **verb**, for example, [`replaceText()`](method-names-analysis.md#replacetext-text-string) returns the primitive value, not part of it. The following examples behave differently cause they return part of the primitive value, having the same method name structure.

#### `getOpening`<mark style="color:orange;">`()`</mark>

\[ get: **verb** ]\[ Opening: **noun** ]\()

```typescript
new Wrapper('<', '>', 'span').getOpening(); // Returns <
new Wrapper('', '>', 'span').getOpening(); // Returns empty string
```

#### `getClosing`<mark style="color:orange;">`()`</mark>

\[ get: **verb** ]\[ Closing: **noun** ]\()

```typescript
new Wrapper('<', '>', 'span').getClosing(); // Returns >
new Wrapper('<', '', 'span').getClosing(); // Returns empty string
```

#### `getText`<mark style="color:orange;">`()`</mark>

\[ get: **verb** ]\[ Text: **noun** ]\()

```typescript
new Wrapper('<', '>', 'span').getText(); // Returns span
new Wrapper('<', '>', '').getText(); // Returns empty string
new Wrapper('<', '>').getText(); // Returns empty string
```

#### Conclusion

These method names refer to **primitive value parts** and return them. We would say the action of **`get`** returns **part** of the primitive value, but the examples of [approach one](method-names-analysis.md#one) make it ambiguous.&#x20;

* The action assigned to this approach is **`get`**.
* The action **`get`** following the object name with the following **noun** indicates return value is a part of the **primitive value**.
* Including the [approach one](method-names-analysis.md#one) action **`get`** does not indicate the return value, but the following **noun** does. The action **`get`** without the following word indicates the return of the primitive value.



### Five

{% hint style="info" %}
The method **without parameters** checks the **existence** of the **part** of the **primitive value** in the object and **returns** the **result**.
{% endhint %}

#### `hasOpening`<mark style="color:orange;">`()`</mark>

\[ has: **verb** ]\[ Opening: **noun** ]\()

```typescript
new Wrap('<', '>', 'span').hasOpening(); // Returns true
new Wrap('', '>', 'span').hasOpening(); // Returns false
```

#### `hasClosing`<mark style="color:orange;">`()`</mark>

\[ has: **verb** ]\[ Closing: **noun** ]\()

```typescript
new Wrapper('<', '>', 'span').hasClosing(); // Returns true
new Wrapper('<', '', 'span').hasClosing(); // Returns false
```

#### `hasText`<mark style="color:orange;">`()`</mark>

\[ has: **verb** ]\[ Text: **noun** ]\()

```typescript
new Wrapper('<', '>', 'span').hasText(); // Returns true
new Wrapper('<', '>', '').hasText(); // Returns false
new Wrapper('<', '>').hasText(); // Returns false
```

#### `isWrapped`<mark style="color:orange;">`()`</mark>

\[ is: **verb** ]\[ Wrapped: **noun** ]\()

```typescript
new Wrapper('<', '>', 'span').isWrapped(); // Returns true
```

#### <mark style="color:red;">`openingHas()`</mark>

\[ opening: **noun** ]\[ Has: **verb** ]\()

```typescript
new Wrap('<', '>', 'span').openingHas();
```

The method name without a **noun** after the **verb** **`has`** seems useless.

#### Conclusion

The method names seem to be obvious, instead of the last one. If the words are swapped their meaning is changed. The [`openingHas()`](method-names-analysis.md#openinghas) method indicates the opening has something, and that something should be provided as the method's parameter.

* The actions assigned to this approach are **`has`**, **`is`**.
* When a **verb** follows the object and a **noun** follows the **verb**, the method checks the **part** of the primitive value.
* When a **noun** following the object refers to the **primitive value part**, the following verb indicates perform on it.



### Six

{% hint style="info" %}
The method **with parameters** checks the **existence** of the **part** of the **primitive value** in the object and **returns** the **result**.
{% endhint %}

#### `hasOpening`<mark style="color:orange;">`(`</mark>`opening: string`<mark style="color:orange;">`)`</mark>

\[ has: **verb** ]\[ Opening: **noun** ]\(\[ opening: **noun** ])

```typescript
new Wrap('<', '>', 'span').hasOpening('<'); // Returns true
new Wrap('<', '>', 'span').hasOpening('{'); // Returns false
new Wrap('', '>', 'span').hasOpening('<'); // Returns false
```

#### `hasClosing`<mark style="color:orange;">`(`</mark>`closing: string`<mark style="color:orange;">`)`</mark>

\[ has: **verb** ]\[ Closing: **noun** ]\(\[ closing: **noun** ])

```typescript
new Wrapper('<', '>', 'span').hasClosing('>'); // Returns true
new Wrapper('<', '>', 'span').hasClosing('{'); // Returns false
new Wrapper('<', '', 'span').hasClosing('>'); // Returns false
```

#### `hasText`<mark style="color:orange;">`(`</mark>`text: string`<mark style="color:orange;">`)`</mark>

\[ has: **verb** ]\[ Text: **noun** ]\(\[ text: **noun** ])

```typescript
new Wrapper('<', '>', 'span').hasText('span'); // Returns true
new Wrapper('<', '>', 'span').hasText('div'); // Returns false
new Wrapper('<', '>', '').hasText(''); // Returns false
new Wrapper('<', '>').hasText(''); // Returns false
```

#### `isWrapped`<mark style="color:orange;">`(`</mark>`opening: string, closing: string`<mark style="color:orange;">`)`</mark>

\[ is: **verb** ]\[ Wrapped: **noun** ]\(\[ opening: **noun**, closing: **noun** ])

```typescript
new Wrapper('<', '>', 'span').isWrapped('<', '>'); // Returns true
new Wrapper('<', '>', 'span').isWrapped('{', '>'); // Returns false
new Wrapper('<', '>', 'span').isWrapped('<', '}'); // Returns false
new Wrapper('<', '>', '').isWrapped('<', '>'); // Returns true
```

#### Conclusion

* The actions assigned to this approach are **`has`**, **`is`**.



### Seven

{% hint style="info" %}
The method **without parameters** checks the **existence** of the **part** of the **primitive value** in the **part** of **the primitive** and **returns** the **result**.
{% endhint %}

#### `textHasOpening`<mark style="color:orange;">`()`</mark>

\[ text: **noun** ]\[ Has: **verb** ]\[ Opening: **noun** ]\()

```typescript
new Wrap('<', '>', 'span').textHasOpening(); // Returns false
new Wrap('<', '>', '<span').textHasOpening(); // Returns true
new Wrap('<', '>', '<span').textHasOpening(); // Returns true
```

The method checks whether the `span` text has the opening `<`.

#### `textHasClosing`<mark style="color:orange;">`()`</mark>

\[ text: **noun** ]\[ Has: **verb** ]\[ Closing: **noun** ]\()

```typescript
new Wrapper('<', '>', 'span').textHasClosing(); // Returns false
```

The method checks whether the `span` text has the closing `>`. Let's add a parameter to the method.

#### `textHasOpening(opening: string)`

\[ text: **noun** ]\[ Has: **verb** ]\[ Opening: **noun** ]\(\[ opening: **noun** ])

```typescript
new Wrap('<', '>', 'span').textHasOpening('<'); // Returns false
new Wrap('<', '>', '<span').textHasOpening('<'); // Returns true
```

The method gets the text and checks whether it contains the given opening chars.

#### `isTextWrapped`<mark style="color:orange;">`(`</mark>`opening: string, closing: string`<mark style="color:orange;">`)`</mark>

\[ is: **verb** ]\[ Text: **noun** ]\[ Wrapped: **noun** ]\(\[ opening: **noun**, closing: **noun** ])

```typescript
new Wrapper('<', '>', '<span>').isTextWrapped('<', '>'); // Returns true
new Wrapper('<', '>', '{span}').isTextWrapped('{', '}'); // Returns true
new Wrapper('<', '>', 'span').isTextWrapped('<', '>'); // Returns false
new Wrapper('<', '>', '').isTextWrapped('<', '>'); // Returns false
new Wrapper('<', '>').isTextWrapped('<', '>'); // Returns false
```

The method checks whether the `span` text has the opening `<` and closing `>`.

#### Conclusion

The use of such methods is questionable. A **noun** following the object indicates the obtaining action similar to the [`openingWrap()`](method-names-analysis.md#openingwrap-opening-string-closing-string) method.

* The actions assigned to this approach are **`has`**, **`is`**.
* If the object is followed by a **noun** the method changes the primitive value **part** and returns it.



### Eight

{% hint style="info" %}
The method **with** **parameters** gets the **parts** of the **primitive value** to perform action appropriate to the **intuitive** **method name** on **given** **method** **parameter(s)**.
{% endhint %}

An interesting thing about this approach is, it seems the same as approach '[three](method-names-analysis.md#three)' above. It also changes the primitive value, but not exactly, because its idea is to use part of the primitive value to change the given method's parameter.

For example, let's try to wrap the text given in the method's parameter with the opening and closing of the `Wrapper` object.

#### `wrapText`<mark style="color:orange;">`(`</mark>`text: string`<mark style="color:orange;">`)`</mark>

\[ wrap: **verb** ]\[ Text: **noun** ]<mark style="color:orange;">**(**</mark>\[ text: **noun** ]<mark style="color:orange;">**)**</mark>

```typescript
// The text is wrapped and returns wrapped text.
new Wrapper('{', '}', 'span').wrapText('div'); // Returns {div}
```

The [`wrap()`](method-names-analysis.md#wrap-opening-string-closing-string) method from [approach three](method-names-analysis.md#three) indicates that the object followed by action [intuitively](../../definitions/intuitive-adjective.md) means the use method's parameters to wrap the primitive value. Because this approach's way of thinking and conflicted parameters with the [`wrapText()`](method-names-analysis.md#wraptext-opening-string-closing-string) method from approach [three](method-names-analysis.md#three), the [`wrapText()`](method-names-analysis.md#wraptext-text-string) method is not intuitive.

We could think the method wraps the text `span` with the provided opening `div`, as in approach '[three](method-names-analysis.md#three)' example above. However, this forces to achieve that the `div` text is wrapped by the opening `{` and closing `}` resulting `{div}`. The method name should indicate its functionality.

The method works like a [`replace()`](method-names-analysis.md#replace-searchvalue-string-replacevalue-string) with the exact meaning of a specific replace in name, and it should return a changed primitive value, like the [`replaceText()`](method-names-analysis.md#replacetext-text-string) method.

Even by swapping the words, the method name is still not intuitive. Cause of thinking that the text `span` is picked from the object, and the action `Wrap` is performed on it.

#### `textWrap`<mark style="color:orange;">`(`</mark>`text: string`<mark style="color:orange;">`)`</mark>

\[ text: **noun** ]\[ Wrap: **verb** ]<mark style="color:orange;">**(**</mark>\[ text: **noun** ]<mark style="color:orange;">**)**</mark>

```typescript
// Returns divspan or {div}
new Wrapper('{', '}', 'span').textWrap('div'); // Returns {div}
```

The question is how to properly differentiate method names to achieve intuitiveness and consistency in method naming for both approaches. The method's name should indicate the use of opening and closing chars to wrap the text given in the method's parameter.

The meaningful solution is the use of **`in`** and **`on`** prepositions, then the methods meaning should indicate use of primitive value **parts**.&#x20;

For example, adding at the end of the `replaceOpening` name the `In` preposition results in the `replaceOpeningIn` method name. The name suggests replacing the opening in something, and the something is the given text.

#### `replaceOpeningIn`<mark style="color:orange;">`(`</mark>`text: string`<mark style="color:orange;">`)`</mark>

\[ replace: **verb** ]\[ Opening: **noun** ]\[ In: **preposition** ]\(\[ text: **noun** ])

```typescript
new Wrapper('{', '}', 'span').replaceOpeningIn('{div}', '<'); // Returns <div}
```

Use the **`On`** preposition after the verb **`Wrap`** should intuitively indicate wrap on something outside.&#x20;

#### `wrapOn(text: string)`

\[ wrap: **noun** ]\[ On: **preposition** ]\(\[ text: **noun** ])

```typescript
new Wrapper('<', '>', 'span').wrapOn('div'); // Returns
```

Crucial question is what the [`wrapOn()`](method-names-analysis.md#wrapon-text-string) method should return, the `Wrap` instance or the primitive value. Because the `Wrapper` contains all the needed properties it seems no sense to return the `Wrap` instance and better to return the primitive value.

#### `isClosingIn`<mark style="color:orange;">`(`</mark>`text: string`<mark style="color:orange;">`)`</mark>

\[ is: **verb** ]\[ Closing: **noun** ]\[ In: **preposition** ]\(\[ text: **noun** ])

```typescript
new Wrapper('{', '}', 'span').isClosingIn('{div}'); // Returns true
new Wrapper('{', '>', 'span').isClosingIn('{div}'); // Returns false
new Wrapper('{', '', 'span').isClosingIn('{div'); // Returns false
```

The method checks whether the given text has the closing of the `Wrapper` instance. It's possible to get part of the primitive value first, and then perform an action on it in the direction specified by the `In` preposition with the name `closingIsIn`.

#### `closingIsIn`<mark style="color:orange;">`(`</mark>`text: string`<mark style="color:orange;">`)`</mark>

\[ closing: **noun** ]\[ Is: **verb** ]\[ In: **preposition** ]\(\[ text: **noun** ])

```typescript
new Wrapper('{', '}', 'span').closingIsIn('{div}'); // Returns true
new Wrapper('{', '>', 'span').closingIsIn('{div}'); // Returns false
new Wrapper('{', '', 'span').closingIsIn('{div'); // Returns false
```

The method checks whether the picked closing of the `Wrapper` instance is in the given text.

#### Conclusion

* Prepositions indicate directions.
* **Intuitively** an action without a noun following the object indicates the change on the primitive value, but the following noun indicates the pick of the primitive value part for possible perform change.
* There is a constant value in the `Wrapper` object, and the difference is in the method's parameters. The `Wrapper` can wrap multiple texts or wrap the part of the primitive value text with multiple opening and closing chars.



### Nine

{% hint style="info" %}
The method **without parameters** converts the **part** of the **primitive value** into another form, for example, object or array.
{% endhint %}

#### `toArray`<mark style="color:orange;">`()`</mark>

\[ to: **preposition** ]\[ Array: **noun** ]\()

```typescript
new Wrapper('<', '>', 'span').toArray(); // Returns ['<', 'span', '>']
```

#### `toWrap`<mark style="color:orange;">`()`</mark>

\[ to: **preposition** ]\[ Wrap: **noun** ]\()

```typescript
new Wrapper('<', '>', 'span').toArray(); // Returns Wrap {'<span>'}
```

## Conclusion

Analysis of possible structures above gives answers that can help prepare some method names useful in the `Wrap` and `Wrapper` objects.

I see it also as a material for creating general principles of designing primitive wrapper objects for angular-package.
