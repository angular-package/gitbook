# isInstance()

### `isInstance()`

Checks if any value is an instance of a given constructor.

Use `isInstance()` or `is.instance()` to check if **any** value is an instance of a given `Constructor`.

{% code title="is-instance.func.ts" %}
```typescript
const isInstance = <Obj, Payload extends object>(
  value: any,
  constructor: Constructor<Obj>,
  callback: ResultCallback<
    Obj,
    { ctor: typeof constructor } & Payload
  > = resultCallback,
  payload?: Payload
): value is Obj =>
  callback(
    isObject(value) &&
    typeof constructor === 'function' &&
    constructor instanceof Function
    ? value instanceof constructor
    : false,
    value,
    { ...payload, ctor: constructor } as any
  );
```
{% endcode %}

### Generic type variables

`Obj`

A generic type variable `Obj`, by default captured from the provided `constructor` indicates the type of `value` parameter via the return type `value is Obj`.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isinstance.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isinstance.md#payload-payload) optional parameter of the [`isInstance()`](isinstance.md#isinstance) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to be an instance of a given `constructor`.

The value of any type to be an instance of a given `constructor`.

#### `constructor: Constructor<Obj>`

A [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global\_attributes/class) or [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) that specifies the type of [`Constructor`](../types/constructor.md).

A \[`class`]\[ts-classes] or \[`function`]\[ts-function] that specifies the type of `Constructor`.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isinstance.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isinstance.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is Obj`

The **return type** is a `boolean` as the result of its statement, indicating the `value` is a generic type variable `Obj` by default of type captured from the supplied `constructor`.

### Returns

The **return value** is a `boolean` indicating whether the provided `value` is an instance of a given `constructor`.

### Example usage

```typescript
// Example usage.
import { isInstance } from '@angular-package/type';

// Classes.
class Some { x = 127; }
class Two { y = 'Lorem ipsum'; }

const SOME = new Some();
const TWO = new Two();

isInstance(TWO, Some); // false
isInstance(SOME, Some); // true
isInstance<Some, object>(TWO, Two); // true and type error

// Example usage with callback and payload.
isInstance(TWO, Some, (result, value, payload) => {
  value // Returns the provided `Two`
  if (payload) {
    payload.className // Returns `'Some'`
    payload.ctor // Returns the provided `Some`
  }
  return result;
}, { className: Some });

// Function constructor.
function functionConstructor(this: any, ...args: any[]): any {
  if (args) {
    args.forEach((arg, index: number) => this[index] = arg[index]);
  }
  return this;
}

const anyInstance: any = new (functionConstructor as any)('First name', 'Sur name', 27);

isInstance(anyInstance, functionConstructor as any); // true
isInstance(new Array(), Array), // Returns `true` as `value is Array`
isInstance(new Boolean(), Boolean), // Returns `true` as `value is Boolean`
isInstance(new Date(), Date), // Returns `true` as `value is Date`
isInstance(new Error(), Error), // Returns `true` as `value is Error`
isInstance(new Function(), Function), // Returns `true` as `value is Function`
isInstance(new Map(), Map), // Returns `true` as `value is Map`
isInstance(new Number(), Number), // Returns `true` as `value is Number`
isInstance(new Object(), Object), // Returns `true` as `value is Object`
isInstance(new RegExp(/^[]/), RegExp), // Returns `true` as `value is RegExp`
isInstance(new Set(), Set), // Returns `true` as `value is Set`
isInstance(new String(), String), // Returns `true` as `value is String`
```
