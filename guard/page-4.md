# guardInstance()

## `guardInstance()`

Guards the value to be an instance of the given [`constructor`](page-4.md#constructor-constructor-less-than-obj-greater-than).

{% code title="guard-instance.func.ts" %}
```typescript
const guardInstance = <
  Obj extends object,
  Payload extends object = object
>(
  value: Obj,
  constructor: Constructor<Obj>,
  callback?: ResultCallback<Obj, { ctor: typeof constructor } & Payload>,
  payload?: Payload
): value is Obj => isInstance(value, constructor, callback, payload);
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/guard/lib/guard-instance.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`Obj`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

A generic type variable `Obj` constrained by [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) indicates captured [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) type of the given [`value`](page-4.md#value-obj) via the [return type](page-4.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](page-4.md#callback-resultcallback-less-than-obj-ctor-typeof-constructor-and-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](page-4.md#callback-resultcallback-less-than-obj-ctor-typeof-constructor-and-payload-greater-than) function and [`payload`](page-4.md#payload-payload) optional parameter of the [`guardInstance()`](page-4.md#guardinstance) function from which it captures its value.

### Parameters

#### `value: Obj`

An [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of a generic type variable [`Obj`](page-4.md#typeextendsanyboolean) to guard and be compared with an instance of a given [`constructor`](page-4.md#constructor-constructor-less-than-obj-greater-than).

#### `constructor: Constructor<Obj>`

A [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global\_attributes/class) or [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function) that specifies the type of the [`Constructor`](../types/constructor.md).

#### `callback?: ResultCallback<Obj, { ctor: typeof constructor } & Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](page-4.md#value-obj) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](page-4.md#payloadextendsobject-object) with optional properties from the provided [`payload`](page-4.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

{% hint style="info" %}
The [`payload`](../types/resultcallback.md#payload-payload) parameter of the [`callback`](page-4.md#callback-resultcallback-less-than-obj-ctor-typeof-constructor-and-payload-greater-than) function consists of the **`ctor`** property under which is set given [`constructor`](page-4.md#constructor-constructor-less-than-obj-greater-than), and it can't be overwritten by the given [`payload`](page-4.md#payload-payload) parameter of the core function.
{% endhint %}

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](page-4.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](page-4.md#callback-resultcallback-less-than-obj-ctor-typeof-constructor-and-payload-greater-than) function.

### Return type

#### `value is Obj`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](page-4.md#value-obj) is a generic type variable [`Obj`](page-4.md#objextendsobject) by default of the type captured from the provided [`value`](page-4.md#value-obj).

### Returns

The **return value** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) indicating whether the [`value`](page-4.md#value-obj) is an instance of a given [`constructor`](page-4.md#constructor-constructor-less-than-obj-greater-than).

## Example usage

```typescript
// Usage example.
import { guardInstance } from '@angular-package/type';

// Person interface.
interface Person {
  firstName?: string;
  surname?: string;
  age?: number;
  sex?: 'male' | 'female';
}

// Class constructor.
class Persons implements Person {
  firstName = '';
  surname = '';
  age = 15;
}

// Function person constructor.
function personFunctionConstructor(this: Person, ...args: any[]): Person {
  if (args) {
    this.firstName = args[0];
    this.surname = args[1];
    this.age = args[2];
    this.sex = args[3];
  }
  return this;
}

const personInstance: Person = new (personFunctionConstructor as any)('First name', 'Sur name', 27);
const personsInstance: Persons = new Persons();

guardInstance(personInstance, personFunctionConstructor as any); // true
guardInstance(personsInstance, Persons); // true
```
