# Investigation

The investigation concerns method naming and involves the names 'wrap' and 'wrapper' and already existing objects of the same name. Before starting an investigation, the [`Wrap`](https://text.angular-package.dev/wrapper/wrap) and [`Wrapper`](https://docs.angular-package.dev/v/text-v1.x/wrapper/wrapper) objects need to be brought closer for their minimal understanding.

## Wrap

The [`Wrap`](https://text.angular-package.dev/wrapper/wrap) object represents the immutable text wrapped by the opening and closing chars, and it is designed to preserve the names of the opening, text, and closing.

### **Definition**

> As a **noun** - _**"**material used for_ [_wrapping_](https://www.merriam-webster.com/dictionary/wrapping)_"_ - Merriam-Webster
>
> As a **noun** - _"_[_paper_](https://dictionary.cambridge.org/dictionary/english/paper)_,_ [_cloth_](https://dictionary.cambridge.org/dictionary/english/cloth)_, or other_ [_material_](https://dictionary.cambridge.org/dictionary/english/material) _that is used to_ [_cover_](https://dictionary.cambridge.org/dictionary/english/cover) _something"_ - Cambridge Dictionary

The wrap is the **thing** that **something** is wrapped in. **Something**, in this case, is the **text**, and the **thing** is the opening and closing characters.

> As a **verb** - _"to put_ [_paper_](https://dictionary.cambridge.org/dictionary/english/paper)_,_ [_cloth_](https://dictionary.cambridge.org/dictionary/english/cloth)_, or other_ [_material_](https://dictionary.cambridge.org/dictionary/english/material) _around something"_ - Cambridge Dictionary

Wrap **something** around another **thing**. **Something**, in this case, is the opening and closing characters, and the **thing** is the **text**.

### Object

The constructor of the [`Wrap`](https://text.angular-package.dev/wrapper/wrap) object initializes by providing a required `opening`, `closing`, and optional `text` to wrap. All the values are a part of the primitive value of this object and are stored separately in private values `#opening`, `#closing`, and `#text`. Access to these properties is by `get` accessors `opening`, `closing` and `text`, so even the parts of the primitive value are immutable.

{% hint style="info" %}
The text is being wrapped only by initialization.
{% endhint %}

```typescript

export class Wrap<
  Opening extends string = string,
  Text extends string = ``,
  Closing extends string = string
> extends String {
  ...

  constructor(opening: Opening, closing: Closing, text: Text = '' as Text) {
    super(`${opening}${text}${closing}`);
    this.#closing = String(closing) as Closing;
    this.#text = String(text) as Text;
    this.#opening = String(opening) as Opening;
  }
    
  ...
}
```

## Wrapper

The [`Wrapper`](https://text.angular-package.dev/wrapper/wrapper) is an extension of the [`Wrap`](https://text.angular-package.dev/wrapper/wrap) object means it represents the immutable wrap of the opening and closing with the additional ability to use it to wrap text.

### Definition

> **noun** - _"a_ [_piece_](https://dictionary.cambridge.org/dictionary/english/piece) _of_ [_paper_](https://dictionary.cambridge.org/dictionary/english/paper)_,_ [_plastic_](https://dictionary.cambridge.org/dictionary/english/plastic)_, or other_ [_material_](https://dictionary.cambridge.org/dictionary/english/material) _used to_ [_cover_](https://dictionary.cambridge.org/dictionary/english/cover) _a_ [_product_](https://dictionary.cambridge.org/dictionary/english/product)_"_ - Cambridge Dictionary
>
> **noun** - _"that in which something is_ [_wrapped_](https://www.merriam-webster.com/dictionary/wrapped)_"_ - Merriam-Webster
>
> **noun** - _"one that_ [_wraps_](https://www.merriam-webster.com/dictionary/wraps)_"_ - Merriam-Webster

It can be understood as **one** or a **machine** that holds the `wrap` to wrap any text by using it. One or a machine is just an object.

### Object

The constructor of the [`Wrapper`](https://docs.angular-package.dev/v/text-v1.x/wrapper/wrapper) object initializes by providing a required `opening`, `closing`, and optional `text` to wrap.

```typescript

export class Wrapper<
  Opening extends string = string,
  Text extends string = '',
  Closing extends string = string
> extends Wrap<Opening, Text, Closing> {
  ...

  // Wrapper constructor.
  constructor(opening: Opening, closing: Closing, text?: Text) {
    super(opening, closing, text);
  }

  ...
}
```

Wrapper's initialization.

```typescript
// Let's initialize the `Wrapper`.
const spanWrapper = new Wrapper('<', '>', 'span');

// Primitive value of the `Wrapper` is <span>.
spanWrapper.valueOf();
```

The examples from previous pages explain how the methods can work on the instance, but the catch is in the `wrap()` method used in two different objects. What does this method do?



### Wrap method in the `Wrapper` object

The `wrap(text: string)` method of the `Wrapper` object with the `text` parameter uses the `<` and `>` of the `Wrapper` instance to wrap the given `text`.

```typescript
// Returns <text> of type "<text>".
new Wrapper('<', '>').wrap('text'); 
```



### Wrap method in the `Text` object

The `Text` object is extended by the `String`, and its primitive value is given text. The `wrap(opening: string, closing: string)` method of `Text` with parameters `opening` and `closing` uses them to wrap the primitive value of the `Text` instance.

```typescript
// Returns <text>.
new Text('text').wrap('<', '>');
```

****

### **Method usage d**ifferences and similarit**i**es

* The **wrap** word **means the same** in both `Text` and `Wrapper` objects - it wraps something.
* The methods return **the same result.**
* The methods have **different parameters** depending on the object.
* The methods **perform the wrap differently** because they perform on different objects with different parameters, but it is still **the same action** of the 'wrap'.
  * The method `wrap()` of the `Text` instance wraps the text of a `Text` instance with given `opening` and `closing` characters in the method.
  * The method `wrap()` of the `Wrapper` instance wraps the given method's text with the opening and closing characters of the `Wrapper` instance.
* There are two functionalities in the same method name.



## Insight

There seems to be no sense to insight the method by a single attribute like consistent or intuitive because they are interdependent, and their meaning is different depending on perspectives. Let's do this because different perspectives should emerge during the read.



**Does the method name is** [**intuitive**](../../definitions/intuitive-adjective.md)**?**

The method means the same in both \`Text\` and \`Wrapper\` objects because they perform the same 'wrap' action. It should be enough to indicate 'wrap' as an **intuitive** method name regardless of the object.



**Does the method name is** [**consistent**](../../definitions/consistent-adjective.md)**?**

The method name is **consistent** because of encoded in generally known naming conventions.

****

**Does the method is** [**intuitive**](../../definitions/intuitive-adjective.md)**?**

The importance of interdependence forces to include at least [functionality](../../definitions/functionality-noun.md) and [consistency](../../definitions/consistency-noun.md) with [intuitiveness](../../definitions/intuitiveness-noun.md).

The method is intuitive because its [functionality](../../definitions/functionality-noun.md) behaves cohesively and [constantly](../../definitions/constantly-adverb.md) to the method name giving the same result, but can be accused as not intuitive because it's called with different parameters depending on the object, which means their functionalities are different despite the same result.

However, when we look at the method as part of a specific object, it seems **intuitive**. If a method is of the `Text` object, we **intuitively** know that we need to provide opening and closing parameters to the `wrap()` method, and if it's of `Wrapper` we know that we need to provide text.&#x20;

If the object name is **not ambiguous**, its functionality too, **intuitive** usage of the `wrap()` method is still possible because we can look at parameters to recognize what type of the wrap method it is.



**Does the method is** [**consistent**](../../definitions/consistent-adjective.md)**?**

The method is **consistent** because the result of its functionality of wrap does the same in both objects.

The method can be accused as **inconsistent** because it's called with different parameters depending on the object, which means their functionalities are **divergent** despite the same result.

However, when we look at the method as part of a specific object, it seems to be **consistent**. We **consistently** know that the method of the `Text` object always has the same parameters, which are different from the `Wrapper` object.

## Conclusion

It is worth checking only the method name, not including the object and its functionality, because then it's possible to achieve constant intuitive method names, at first sight, indicating its meaning. The need is also to have the same parameters. They act similar to a function. Similar because methods pick the data from an instance.

There are **two** **types** of methods, **first**, changes the primitive value of a specified object with or without parameters, and **second**, uses the primitive value to change a given method's parameter.

There are **two functionalities**, and the object should not have both functionalities in one method cause of parameters conflict or even with additional parameters because of losing its simplicity. To achieve consistency and intuitiveness, we need to separate both functionalities using different method names, which can be `wrap()` and `wrapText()` of the exact meaning. It should be noted that the additional method increases the object's complexity.

Crucial is to have an intuitive naming. The `wrap` refers that the text to be wrapped is in the instance. The `wrapText` indicates that the text to be wrapped needs to be provided in the method parameter.&#x20;

Let's analyze naming the methods to see it's not simple.
