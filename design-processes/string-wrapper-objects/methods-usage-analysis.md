# Methods usage analysis

The [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/String) primitive wrapper object is selected to research how some of its methods perform on the instance to understand [**intuitiveness**](../../definitions/intuitiveness-noun.md) and [**consistency**](../../definitions/consistency-noun.md) in native objects. Below are possible ways methods work on an instance broken down into nine approaches, and each contains a list of words picked from examples for a better understanding of the naming methodology and further analysis.

### Primitive value part

The text contains the keyword '_**part of the primitive value**_', and the following example clarifies its meaning.&#x20;

```typescript
// Define a new `Text` class.
class Text extends string {
  constructor(
    public prefix: string, // Part of the primitive value.
    public text: string,  // Part of the primitive value.
    public suffix: string // Part of the primitive value.
  ) {
    super(`${prefix}${text}${suffix}`); // The primitive value.
  }
}

// Returns <span>
new Text('<', 'span', '>').valueOf();
```

The primitive value consists of `prefix`, `text`, and `suffix` properties, and each of them is a **part** of the **primitive value**.

## Approaches

### One

{% hint style="info" %}
The method **without** **parameters** gets the **primitive value** and returns a **primitive value**.
{% endhint %}

There are two [`valueOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/valueOf) and [`toString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/toString) methods that match the description.

```typescript
// Define a new `String` object.
const text = new String('text');

// Returns 'text';
text.valueOf();

// Returns 'text';
text.toString();
```

#### Words

* `value` ([noun](../../definitions/noun-noun.md))
* `to` ([preposition](../../definitions/preposition-noun.md))
* `Of` ([preposition](../../definitions/preposition-noun.md))
* `String` ([noun](../../definitions/noun-noun.md))



### Two

{% hint style="info" %}
The method **without** **parameters** gets the **primitive value** and performs an action on it based on the **intuitive** method name, and **returns** the **changed primitive value**.
{% endhint %}

There are among others [`big()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/big), [`blink()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/blink), [`bold()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/bold), [`fixed()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/fixed), [`italics()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/italics), [`small()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/small), [`strike()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/strike), `sub()`, `sup()`, [`toLocaleLowerCase()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/toLocaleLowerCase), [`toLocaleUpperCase()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/toLocaleUpperCase), [`toUpperCase()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/toUpperCase), [`trimEnd()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/trimEnd), `trimLeft()`, `trimRight()`, [`trimStart()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/trimStart) methods.

For example, the deprecated [`bold()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/bold) method gets the primitive value of a `text` string object and returns a modified `string` tagged by the Html `<b>` tag.

```typescript
// Define a new `String` object.
const text = new String('text');

// Returns <b>text</b> of `string`.
text.bold();
```

#### Words

* `to` ([noun](../../definitions/noun-noun.md))
* `Upper` ([adjective](../../definitions/adjective-noun.md))
* `Case` ([noun](../../definitions/noun-noun.md))
* `trim` ([noun](../../definitions/noun-noun.md))
* `Left` ([noun](../../definitions/noun-noun.md))
* `Right` ([noun](../../definitions/noun-noun.md))



### Three

{% hint style="info" %}
The method **with** **parameters** gets the **primitive value** and performs an action on it based on the **intuitive** method name with the **use** of its **parameters** and **returns** the **changed primitive value**.
{% endhint %}

For example, the [`replace()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/replace) method gets the primitive value of the `text` string object and returns a modified `string` according to the given parameters.

```typescript
// Define a new `String` object.
const text = new String('text');

// Returns 'tExt' of `string`.
text.replace('e', 'E');

// Returns 'ex' of `string`.
text.substr(1, 2);

// Returns 'texttext'
text.repeat(2);
```

#### Words

* `repeat` ([verb](../../definitions/verb-noun.md))
* `replace` ([verb](https://app.gitbook.com/s/egwDY3Lznv3ifnxKVeRI/c/QmdAEHTvODKntFFpwMqq/definitions/verb))
* `substr` ([noun](../../definitions/noun-noun.md)?)



### Four

{% hint style="info" %}
The method **without** **parameters** gets **part** of the **primitive value** and **returns it**.
{% endhint %}

Let's define the `Text` object and extend it with the `String` to achieve this approach. The method `getPrefix()` returns part of the primitive value `prefix`, and the `getText()` method returns part of the primitive value `text`.

```typescript
// Create a new `Text` object.
class Text extends String {
  constructor(public text: string, public prefix?: string) {
    super(`${prefix}${text}`);
  }
  public getPrefix(): string {
    return this.prefix;
  }
  public getText(): string {
    return this.text;
  }
}

// Define a text with prefix.
const text = new Text('my text', '<<');

// Returns Text {'<<my text', text: 'my text', prefix: '<<'}.
text;

// Returns <<.
text.getPrefix();

// Returns my text.
text.getText();
```

#### Words

* `get` ([verb](../../definitions/verb-noun.md))
* `Prefix` ([noun](../../definitions/noun-noun.md))
* `Text` ([noun](../../definitions/noun-noun.md))



### Five

{% hint style="info" %}
The method **without parameters** checks the **existence** of the **part** of the **primitive value** in the object and **returns** the **result**.
{% endhint %}

Let's define the `Text` object and extend it with the `String` to achieve this approach. The `hasPrefix()` method checks whether the `Text` object has an optional prefix, and the method `hasText()` seems useless because the `text` it's required, but not really.

```typescript
// Create a new `Text` object.
class Text extends String {
  constructor(public text: string, public prefix?: string) {
    super(`${prefix ? prefix : ''}${text}`);
  }
  public hasPrefix(): boolean {
    return this.prefix !== undefined ;
  }
  public hasText(): boolean {
    return this.text !== undefined;
  }
}

// Define a text with prefix.
const text = new Text('my text', '<<');

// Returns Text {'<<my text', text: 'my text', prefix: '<<'}.
text;

// Returns true.
text.hasPrefix();

// Returns true. (noun) (noun)
text.hasText();
```

#### Words

* `has` ([verb](../../definitions/verb-noun.md))
* `Text` ([noun](../../definitions/noun-noun.md))
* `Prefix` ([noun](../../definitions/noun-noun.md))



### Six

{% hint style="info" %}
The method **with parameters** checks the **existence** of the **part** of the **primitive value** in the object and **returns** the **result**.
{% endhint %}

```typescript
// Create a new `Text` object.
class Text extends String {
  constructor(public text: string, public prefix?: string) {
    super(`${prefix ? prefix : ''}${text}`);
  }
  public hasPrefix(prefix: string): boolean {
    return this.prefix !== undefined && this.prefix === prefix;
  }
  public hasText(text: string): boolean {
    return this.text !== undefined && this.text === text;
  }
}

// Define a text with prefix.
const text = new Text('my text', '<<');

// Returns Text {'<<my text', text: 'my text', prefix: '<<'}.
text;

// Returns true.
text.hasPrefix('<<');

// Returns true.
text.hasText('my text');
```

#### Words

* `has` ([verb](../../definitions/verb-noun.md))
* `Prefix` ([noun](../../definitions/noun-noun.md))
* `Text` ([noun](../../definitions/noun-noun.md))



### Seven

{% hint style="info" %}
The method **without parameters** checks the **existence** of the **part** of the **primitive value** in the **part** of **the primitive** and **returns** the **result**.
{% endhint %}

Let's define the `Text` object and extend it with the `String` to achieve this approach. The `textHasPrefix()` method checks whether the `text` includes the `prefix` of the primitive value. The same does `hasTextPrefix()` method.

```typescript
// Create a new `Text` object.
class Text extends String {
  constructor(public text: string, public prefix?: string) {
    super(`${prefix}${text}`);
  }
  public textHasPrefix(): boolean {
    return typeof this.prefix === 'string' && this.text.includes(this.prefix);
  }
  public hasTextPrefix(): boolean {
    return typeof this.prefix === 'string' && this.text.includes(this.prefix);
  }
}

// Define a text with prefix.
const text = new Text('my text', '<<');

// Returns Text {'<<my text', text: 'my text', prefix: '<<'}.
text;

// Returns false.
text.textHasPrefix();

// Returns false. Method is not intuitive.
text.hasTextPrefix();
```

The example shows some possibilities of naming the methods and potential conflict with intuitiveness.

#### Words

* `text` ([noun](../../definitions/noun-noun.md))
* `Has` ([verb](../../definitions/verb-noun.md))
* `Prefix` ([noun](../../definitions/noun-noun.md))



### Eight

{% hint style="info" %}
The method **with** **parameters** gets the **parts** of the **primitive value** to perform action appropriate to the **intuitive** **method name** on **given** **method** **parameter(s)**.
{% endhint %}

Let's define the `Replacer` object to explain. The `replaceInText()` method gets the parts of the object to perform replacing on a given text. The example does not refer directly to the [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/String) method, but a custom method showing a possibility of different usage of the `replace()` method.

```typescript
// Define a new `String` object.
const text = new String('text');

// Create a new `Replacer` object.
class Replacer extends String {
  constructor(public searchValue: string, public replaceValue: string) {
    super(`${searchValue}=${replaceValue}`);
  }
  public replaceInText(text: string | String): string {
    return text.replace(this.searchValue, this.replaceValue);
  }
  public replaceTextIn(text: string | String): string {
    return text.replace(this.searchValue, this.replaceValue);
  }
  public inText(text: string | String): string {
    return text.replace(this.searchValue, this.replaceValue);
  }
}

// Define a replacer.
const replacer = new Replacer('e', 'E');

// Returns tExt of `string`.
replacer.replaceInText(text);

// Returns tExt of `string`.
replacer.replaceTextIn(text);

// Returns tExt of `string`.
replacer.inText(text);
```

The last example of the `inText()` method indicates the relation between the object and method name because the object's name suggests action. The same we can do with the [first](methods-usage-analysis.md#approach-1) approach above.

```typescript
// Imagine the class bold contains <b></b> and uses it to bold any text.
const bold = new bold();

// Returns <b>bolded</b> of `string`.
bold.text('bolded');

// Or to bold multiple texts.
// Returns ['<b>bolded</b>', '<b>also bolded</b>']
bold.text(['bolded', 'also bolded']);
```

#### Words

* `replace` ([verb](../../definitions/verb-noun.md))
* `In` ([preposition](../../definitions/preposition-noun.md))
* `Text` ([noun](../../definitions/noun-noun.md))



### Nine

{% hint style="info" %}
The method **without parameters** converts the **part** of the **primitive value** into another form, for example, object or array.
{% endhint %}

```typescript
// Create a new `Text` object.
class Text extends String {
  constructor(public text: string, public prefix?: string) {
    super(`${prefix ? prefix : ''}${text}`);
  }
  public toArray(): [ string | undefined, string ] {
    return [this.prefix, this.text ];
  }
  public toObject(): { [index: string]: string } {
    return {
      0: `${this.prefix}${this.text}`
    };
  }
}

// Define a text with prefix.
const text = new Text('my text', '<<');

// Returns Text {'<<my text', text: 'my text', prefix: '<<'}.
text;

// Returns ['<<', 'my text']
text.toArray();

// Returns {0: '<<my text'}.
text.toObject();
```

**Words**

* `to` ([verb](../../definitions/verb-noun.md))
* `Object` ([noun](../../definitions/noun-noun.md))
* `Array` ([noun](../../definitions/noun-noun.md))

## Conclusion

The **main goal** is to properly **differentiate** method names that work on the primitive value from those using the primitive value on the given method's parameters.

Misuse of words with improper order in the method name results in a different meaning and can lead to non-intuitiveness and inconsistency in the method usage and naming. To avoid such problems it is necessary to have a **deeper** understanding of the words **consistent** and **intuitive**.
