# isClass()

## `isClass()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is a [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function) type or the type obtained from its [`object` class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/toString#using\_tostring\_to\_detect\_object\_class) equal to `'function'` and an instance of [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions). It also confirms it's a [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global\_attributes/class) by checking whether the [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function) converted with [`Function.prototype.toString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function/toString) to `string` contains the word `class` at the beginning.

{% code title="is-class.func.ts" %}
```typescript
const isClass = <Class = Function, Payload extends object = object>(
  value: any,
  callback: ResultCallback<any, Payload> = resultCallback,
  payload?: Payload
): value is Class =>
  callback(
    typeof value === 'function' ||
    (typeOf(value) === 'function' && value instanceof Function)
    ? /class/.test(Function.prototype.toString.call(value).slice(0, 5))
    : false,
    value,
    payload
  );
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/is/lib/is-class.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`Class`**</mark>**`=`**<mark style="color:green;">**`Function`**</mark>

The `Class` generic type variable indicates the [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global\_attributes/class) type of the given [`value`](isclass.md#value-any) via the [return type](isclass.md#return-type), by default [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function).

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](isclass.md#callback-resultcallback-less-than-any-payload-greater-than) function and [`payload`](isclass.md#payload-payload) optional parameter of the [`isClass()`](isclass.md#isclass) function from which it captures its value.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](isclass.md#value-any) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](isclass.md#payloadextendsobject-object) with optional properties from the provided [`payload`](isclass.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](isclass.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](isclass.md#callback-resultcallback-less-than-any-payload-greater-than) function.

### Return type

#### `value is`<mark style="color:green;">`Class`</mark>

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](isclass.md#value-any) is a generic type variable [`Class`](isclass.md#class-function) by default [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](isclass.md#value-any) is a [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global\_attributes/class).

## Example usage

### Basic example

```typescript
// Example usage.
import { isClass } from '@angular-package/type';

class Class { x = 5; }
const FUNC = (x: number): any => x + 5;

isClass<Class>(Class); // Returns `true` as `value is Class`
isClass(FUNC); // Returns `false` as `value is Function`
isClass(() => 5); // Returns `false` as `value is Function`
```

### Callback and payload parameters

```typescript
// Callback and payload parameters example usage.
import { isClass } from '@angular-package/type';

isClass(() => 5, (result, value, payload) => {
  value // Returns `() => 5`
  if (payload) {
    result // Returns `false`
    payload.c // Returns `class Class`
  }
  return result;
}, { c: Class }); // Returns `false` as `value is Function`
```
