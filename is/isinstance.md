# isInstance()

## `isInstance()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is an instance of a given [`constructor`](isinstance.md#constructor-constructor-less-than-obj-greater-than).

{% code title="is-instance.func.ts" %}
```typescript
const isInstance = <Obj, Payload extends object>(
  value: any,
  constructor: Constructor<Obj>,
  callback: ResultCallback<
    any,
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

#### <mark style="color:green;">`Obj`</mark>

A generic type variable `Obj`, by default captured from the provided [`constructor`](isinstance.md#constructor-constructor-less-than-obj-greater-than), indicates the type of generic type [`Constructor`](../types/constructor.md), and the type of [`value`](isinstance.md#value-any) parameter via the [return type](isinstance.md#return-type) `value is Obj`.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isinstance.md#callback-resultcallback-less-than-any-ctor-typeof-constructor-and-payload-greater-than) function and [`payload`](isinstance.md#payload-payload) optional parameter of the [`isInstance()`](isinstance.md#isinstance) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to be an instance of a given [`constructor`](isinstance.md#constructor-constructor-less-than-obj-greater-than).

#### `constructor: Constructor<Obj>`

A [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global\_attributes/class) or [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) that specifies the type of [`Constructor`](../types/constructor.md).

#### `callback: ResultCallback<any, { ctor: typeof constructor } & Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isinstance.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isinstance.md#payloadextendsobject) with optional properties from the provided [`payload`](isinstance.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

{% hint style="info" %}
The [`payload`](../types/resultcallback.md#payload-payload) parameter of the [`callback`](../types/resultcallback.md) function consists of the [`ctor`](isinstance.md#constructor-constructor-less-than-obj-greater-than) property  given in the [`constructor`](isinstance.md#constructor-constructor-less-than-obj-greater-than) parameter of the core function, and it can't be overwritten by the given [`payload`](isinstance.md#payload-payload) parameter of the core function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isinstance.md#payloadextendsobject) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isinstance.md#callback-resultcallback-less-than-any-ctor-typeof-constructor-and-payload-greater-than) function.

### Return type

#### `value is Obj`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement, indicating the [`value`](isinstance.md#value-any) is a generic type variable [`Obj`](isinstance.md#obj) by default of type captured from the supplied [`constructor`](isinstance.md#constructor-constructor-less-than-obj-greater-than).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isinstance.md#value-any) is an instance of a given [`constructor`](isinstance.md#constructor-constructor-less-than-obj-greater-than).

## Example usage

### Basic usage

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

### Parameters `callback` and `payload`&#x20;

```typescript
// Example usage with callback and payload.
import { isInstance } from '@angular-package/type';

// Classes.
class Some { x = 127; }
class Two { y = 'Lorem ipsum'; }

const SOME = new Some();
const TWO = new Two();

isInstance(TWO, Some, (result, value, payload) => {
  value // Returns the provided `Two`
  if (payload) {
    payload.className // Returns `'Some'`
    payload.ctor // Returns the provided `Some`
  }
  return result;
}, { className: Some });
```

### Function constructor

```typescript
// Example usage with function constructor.
import { isInstance } from '@angular-package/type';

// Function constructor.
function functionConstructor(this: any, ...args: any[]): any {
  if (args) {
    args.forEach((arg, index: number) => this[index] = arg[index]);
  }
  return this;
}

const anyInstance: any = new (functionConstructor as any)('First name', 'Sur name', 27);
isInstance(anyInstance, functionConstructor as any); // true
```
