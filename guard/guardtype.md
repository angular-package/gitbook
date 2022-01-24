# guardType()

## `guardType()`

Guards the value to be a type of given [`type`](guardtype.md#type-types-less-than-t-greater-than).

{% code title="guard-type.func.ts" %}
```typescript
const guardType = <T extends Type, Payload extends object = object>(
  value: T,
  type: Types<T>,
  callback?: ResultCallback<T, Payload>,
  payload?: Payload
): value is T => isType(value, type, callback, payload);
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/5.0.x/src/guard/lib/guard-type.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`T`**</mark>**`extends`**<mark style="color:green;">**`Type`**</mark>

A generic type variable `T` constrained by generic type [`Type`](../types/type.md) indicates captured type of the supplied [`value`](guardtype.md#value-type) via the [return type](guardtype.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardtype.md#callback-resultcallback-less-than-bigint-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardtype.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardtype.md#payload-payload) optional parameter of the [`guardType()`](guardtype.md#guardtype) function from which it captures its value.

### Parameters

#### `value: T`

The value of a generic type variable [`T`](guardtype.md#textendstype) constrained by generic type [`Type`](../types/type.md), by default of the type captured from itself, to guard.

#### `type: Types<T>`

The value of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) or [`Constructor<T>`](../types/constructor.md) type of the [`Types`](../types/types.md) indicates against which type a given [`value`](guardtype.md#value-t) is checked.

#### `callback?: ResultCallback<T, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](guardtype.md#payloadextendsobject) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardtype.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardtype.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is`<mark style="color:green;">`T`</mark>

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](guardtype.md#value-t) is a generic type variable [`T`](guardtype.md#textendstype) by default of the type captured from the supplied [`value`](guardtype.md#value-t).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the [`value`](guardtype.md#value-t) is a type from a given [`type`](guardtype.md#type-types-less-than-t-greater-than) of the [`Types`](../types/types.md).

### Example usage

```typescript
// Example usage.
import { guardType } from '@angular-package/type';

// Person interface.
interface PersonData { firstName: string; }

// Class.
class Person {}

// Object.
const someone: Person = new Person();

const object: PersonData = { firstName: 'firstName' };
guardType(object, 'object'); // true; return type `value is PersonData`

let letObject: PersonData = { firstName: 'firstName' };
guardType(letObject, 'object'); // true; return type `value is PersonData`

function myPerson(person: Person): Person { return person; }
guardType(myPerson, 'function'); // true; return type `value is (person: Person) => Person`

// string.
const firstName = 'firstName';
guardType(firstName, 'string'); // true; return type `value is "firstName"`
let letFirstName = 'firstName';
guardType(letFirstName, 'string'); // true; return type `value is string`

// number.
const age = 5;
guardType(age, 'number'); // true; return type `value is 5`
let letAge = 5;
guardType(letAge, 'number'); // true; return type `value is number`

// null.
const myNull = null;
guardType(myNull, 'null'); // true; return type `value is null`

// bigint
const oldAge = 1n;
guardType(oldAge, 'bigint'); // true; return type `value is 1n`
let letOldAge = 1n;
guardType(letOldAge, 'bigint'); // true; return type `value is bigint`

// Boolean.
const question = true;
guardType(question, 'boolean'); // true; return type `value is true`
let letQuestion = true;
guardType(letQuestion, 'boolean'); // true; return type `value is true`

// Undefined.
const und = undefined;
guardType(und, 'undefined'); // true; return type `value is undefined`
let letUndefined ;
guardType(letUndefined, 'undefined'); // true; return type `value is undefined`

// Symbol.
guardType(Symbol(firstName), 'symbol'); // true; return type `value is symbol`

// Instance.
guardType(someone, Person); // true; return type `value is Person`
```
