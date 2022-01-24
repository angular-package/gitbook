# Recognize value

To determine any value is to know what type and instance it can be and when and what function or operator should be used to specify it. To help this, the [`recognizeValue()`](https://type.angular-package.dev/helper/recognizevalue) function was created, and it seems not enough because it must be known the risks of using operators and functions.

The following list contains "tools" to recognize types and instances in the [`recognizeValue()`](https://type.angular-package.dev/helper/recognizevalue) function.

#### Function

* ``[`isClass()`](https://type.angular-package.dev/is/isclass),
* ``[`isClass()`](https://type.angular-package.dev/is/isclass),
* ``[`isFinite()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/isFinite),
* ``[`isFunction()`](https://type.angular-package.dev/is/isfunction),
* ``[`isNaN()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/isNaN),
* ``[`typeOf()`](https://type.angular-package.dev/helper/typeof),

#### Method

* ``[`Array.isArray()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/isArray),
* ``[`Number.isInteger()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number/isInteger),
* ``[`Number.isFinite()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number/isFinite),
* ``[`Number.isNaN()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number/isNaN),
* ``[`Number.isSafeInteger()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number/isSafeInteger),
* ``[`Object.hasOwnProperty()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/hasOwnProperty)``

#### Operator

* ``[`in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in) operator,
* [`instanceof`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof) operator,
* [`typeof`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof) operator,

Let's use them to create `recognizeValue()` function.

## `recognizeValue()`

Gets recognized types and instances of given `value`.

{% code title="recognize-value.func.ts" %}
```typescript
const recognizeValue = (
  value: any,
  onlyTrue: boolean = true,
  instances: any[] = []
): OfRecognized => {
  // Recognize types.
  const ofRecognized: OfRecognized = {
    'Array.isArray': Array.isArray(value),
    isClass: is.class(value),
    isFunction: is.function(value),
    'Number.isInteger': Number.isInteger(value),
    'Number.isFinite': Number.isFinite(value),
    'Number.isNaN': Number.isNaN(value),
    'Number.isSafeInteger': Number.isSafeInteger(value),
    typeOf: typeOf(value),
    typeof: typeof value,
  };

  try { Object.assign(ofRecognized, { isFinite: isFinite(value) }); } catch (e) {}
  try { Object.assign(ofRecognized, { isNaN: isNaN(value) }); } catch (e) {}

  // Recognize instances.
  RECOGNIZE_INSTANCES.concat(instances as any).forEach((instance) => (
    Object.assign(ofRecognized, { [instance.name]: value instanceof instance })
  ));

  // If only true remove false.
  if (is.true(onlyTrue)) {
    Object.keys(ofRecognized).filter((type: string) =>
      is.false(ofRecognized[type as keyof OfRecognized])
        ? delete ofRecognized[type as keyof OfRecognized]
        : true
    );
  }
  return ofRecognized;
};
```
{% endcode %}

### Parameters

#### `value: any`

The `value` of any type to recognize.

#### `onlyTrue: boolean`

Determines whether to show only recognized as `true`.

#### `instances: any[]`

An optional array of objects to check by using [`instanceof`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof) operator.

### Returns

The **return value** is an object of types and instances recognized as `true` or all even those recognized as `false`.

## Recognized instances

An `Array` of default objects that is used by the [`recognizeValue()`](https://type.angular-package.dev/helper/recognizevalue) function to check the value instance by using the [`instanceof`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof) operator. It can be expanded by the provided [`instances`](recognize-value.md#instances-any) parameter.

```typescript
const RECOGNIZE_INSTANCES = [
  Array,
  ArrayBuffer,
  Boolean,
  DataView,
  Date,
  Error,
  EvalError,
  Float32Array,
  Float64Array,
  Function,
  Int16Array,
  Int32Array,
  Int8Array,
  Map,
  Number,
  Object,
  Promise,
  RangeError,
  ReferenceError,
  RegExp,
  Set,
  Storage,
  String,
  SyntaxError,
  TypeError,
  URIError,
  Uint16Array,
  Uint32Array,
  Uint8Array,
  Uint8ClampedArray,
  WeakMap,
  WeakSet
];
```
