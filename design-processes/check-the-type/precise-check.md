# Precise check

To precisely check the type of any value it needs to check the `Object.prototype` class of that value and [`typeOf()`](https://type.angular-package.dev/helper/typeof) is perfect for this. Read the following articles to learn more.

* [Using `toString()` to detect object class.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/toString#using\_tostring\_to\_detect\_object\_class)
* [Symbol.toStringTag](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Symbol/toStringTag)
* [The Best Way to Type Check in Vanilla JS.](https://javascript.plainenglish.io/the-best-way-to-type-check-in-vanilla-js-55197b4f45ec)
* [Using JavaScript Symbol.toStringTag for objects types description.](https://dev.to/cherif\_b/using-javascript-tostringtag-for-objects-types-description-15hc)

**Mozilla.org** documentation describes this way of checking as unreliable. The problem and at the same time some kind of solution with this approach of checking is, it's possible to change the class name of the object.

> _"Using `toString()` in this way is unreliable; objects can change the behavior of `Object.prototype.toString()` by defining a `Symbol.toStringTag` property, leading to unexpected results."_ - mozilla.org

There are some examples in the first link above, and below under the usage section of [`typeOf()`](precise-check.md#example-usage).

## **`typeOf()`**

Function to detect object class name.

```typescript
const typeOf = (value: any): string =>
  Object.prototype.toString.call(value).slice(8, -1).toLowerCase();
```

### **Example usage**

```typescript
// Example usage.
/*
  Date.
*/
const myDate = new Date();
Object.prototype.toString.call(myDate); // [object Date]

// Change the class name to `Person`.
Object.assign(myDate, {
  get [Symbol.toStringTag](): string {
    return 'Person';
  }
});

// Instead of `Date`, there is `Person`.
Object.prototype.toString.call(myDate); // [object Person]

// This is a solution for just an object !
const person = {
  firstName: 'My name',
  get [Symbol.toStringTag](): string {
    return 'Person';
  }
};

// Now the object can be found by using.
typeOf(person) === 'person';

/*
  Example of the `RegExp` that is treated as `Date`.
*/
const myRegExp = new RegExp(/^/);
Object.prototype.toString.call(myRegExp); // [object RegExp]

// Change the class name to `Date`.
Object.assign(myRegExp, {
  get [Symbol.toStringTag](): string {
    return 'Date';
  }
});

// Instead of `RegExp`, there is `Date`.
Object.prototype.toString.call(myRegExp); // [object Date]
myRegExp instanceof RegExp // Confirms, it's a `RegExp` not a `Date`.
```

### **Summary**

Because of the simplicity of manipulating objects, the [`typeOf()`](https://type.angular-package.dev/helper/typeof) function cannot be used without other ways of confirming the type, like e.g. with the help [`instanceof`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof) operator. On the other hand, the [`instanceof`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof) operator may result in unexpected results what can be read in **Mozilla.org** documentation [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof#instanceof\_and\_multiple\_context\_e.g.\_frames\_or\_windows) in the section **instanceof and multiple context (e.g. frames or windows)**:

> _Different scopes have different execution environments. This means that they have different built-ins (different global object, different constructors, etc.). This may result in unexpected results. For instance, `[] instanceof window.frames[0].Array` will return `false`, because `Array.prototype !== ``window.frames[0].Array.prototype` and arrays inherit from the former._

The `angular-package/type` was created with the above in mind.
