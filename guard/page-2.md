# guardClass()

## `guardClass()`

Guards the value to be a [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global\_attributes/class) of generic type variable [`Class`](page-2.md#classextendsfunction).

{% code title="guard-class.func.ts" %}
```typescript
const guardClass = <
  Class extends Function,
  Payload extends object = object
>(
  value: Class,
  callback?: ResultCallback<Class, Payload>,
  payload?: Payload
): value is Class => isClass(value, callback, payload);
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">**`Class`**</mark>**`extends`**<mark style="color:green;">**`Function`**</mark>

A generic type variable `Class` constrained by [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) indicates the captured type of the given [`value`](page-2.md#value-class) via the [return type](page-2.md#return-type) and the [`value`](../type/resultcallback.md#value-value) parameter of the provided [`callback`](page-2.md#callback-resultcallback-less-than-class-payload-greater-than) function [`ResultCallback`](../type/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../type/resultcallback.md#payload-payload) of the supplied [`callback`](page-2.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](page-2.md#payload-payload) optional parameter of the [`guardClass()`](page-2.md#guardclass) function from which it captures its value.

### Parameters

#### `value: Class`

The [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global\_attributes/class) of a generic type variable [`Class`](page-2.md#classextendsfunction) to guard.

#### `callback?: ResultCallback<Class, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../type/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](page-2.md#payloadextendsobject-object) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](page-2.md#payloadextendsobject-object) is assigned to the [`payload`](../type/resultcallback.md#payload-payload) of the given [`callback`](page-2.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is Class`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](page-2.md#value-class) is a generic type variable [`Class`](page-2.md#classextendsfunction) by default of type captured from the supplied [`value`](page-2.md#value-class).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](page-2.md#value-class) is a [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global\_attributes/class) of a generic type variable [`Class`](page-2.md#classextendsfunction).

### Example usage

```typescript
// Example usage.
import { guardClass } from '@angular-package/type';

type PlusFunction = (...param: any) => any;

/**
 * typeof === 'function'
 * instanceof Function === true
 * instanceof Object === true
 */
const FUNCTION: PlusFunction = (x: number, y: string): any => x + y;

/**
 * typeof === 'function'
 * instanceof Class === false
 * instanceof Function === true
 * instanceof Object === true
 */
class Class {

  1030405027 = 'my new number';
  5 = 'my number';

  firstName = 'My name';
  surname = 'Surname';

  x = NUMBER;
  y = STRING;

  get [NUMBER](): number {
    return this.x;
  }
  get [STRING](): string {
    return this.y;
  }

  get [SYMBOL_NUMBER](): number {
    return this.x;
  }

  get [SYMBOL_STRING](): string {
    return this.y;
  }
}

guardClass(FUNCTION); // false
guardClass<Class>(FUNCTION); // type error
```
