# Recognized instances

## Recognized instances

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) of default objects that is used by the [`recognizeValue()`](https://type.angular-package.dev/helper/recognizevalue) function to check the value instance by using the [`instanceof`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof) operator. It can be expanded by the provided [`instances`](recognized-instances.md#instances-any) parameter.

{% code title="recognize-instances.const.ts" %}
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
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/recognize/src/recognize-instances.const.ts" %}
