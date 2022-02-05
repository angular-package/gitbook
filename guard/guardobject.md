# guardObject()

## `guardObject()`

Guards the value to be an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of a generic type variable [`Obj`](guardobject.md#objextendsobject). The function guards only generic objects, not **specific** objects.

{% code title="guard-object.func.ts" %}
```typescript
const guardObject = <
  Obj extends object,
  Payload extends object = object
>(
  value: Obj,
  callback?: ResultCallback<Obj, Payload>,
  payload?: Payload
): value is Obj => isObject(value, callback, payload);
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/guard/lib/guard-object.func.ts" %}

### Generic type variables

#### <mark style="color:green;">**`Obj`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

A generic type variable `Obj` constrained by [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) indicates captured [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) type of the given [`value`](guardobject.md#value-obj) via the [return type](guardobject.md#return-type) and the [`value`](../types/resultcallback.md#value-value) parameter of the provided [`callback`](guardobject.md#callback-resultcallback-less-than-type-payload-greater-than) function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of optional parameter [`payload`](../types/resultcallback.md#payload-payload) of the supplied [`callback`](guardobject.md#callback-resultcallback-less-than-type-payload-greater-than) function and [`payload`](guardobject.md#payload-payload) optional parameter of the [`guardObject()`](guardobject.md#guardobject) function from which it captures its value.

### Parameters

#### `value: Obj`

An [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of a generic type variable [`Obj`](guardobject.md#objextendsobject), by default of the type captured from itself to guard.

#### `callback?: ResultCallback<Type, Payload>`

The optional callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the [`value`](guardobject.md#value-obj) that has been checked, the [`result`](../types/resultcallback.md#result-boolean) of this check, and [`payload`](../types/resultcallback.md#payload-payload) of generic type variable [`Payload`](guardobject.md#payloadextendsobject-object) with optional properties from the provided [`payload`](guardobject.md#payload-payload), to handle them before the [`result`](../types/resultcallback.md#result-boolean) return. By default, it uses [`resultCallback()`](../helper/resultcallback.md) function.

#### `payload?: Payload`

An optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of the generic type variable [`Payload`](guardobject.md#payloadextendsobject-object) is assigned to the [`payload`](../types/resultcallback.md#payload-payload) of the given [`callback`](guardobject.md#callback-resultcallback-less-than-bigint-payload-greater-than) function.

### Return type

#### `value is Obj`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the [`value`](guardobject.md#value-obj) is an [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) of a generic type variable [`Obj`](guardobject.md#objextendsobject), by default of type captured from the supplied [`value`](guardobject.md#value-obj).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](guardobject.md#value-obj) is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object)[ ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object)of a generic type variable [`Obj`](guardobject.md#objextendsobject).

## Example usage

```typescript
// Example usage.
import { guardObject } from '@angular-package/type';

class Person {}
const o = {};
const p = new Person();

guardObject(o); // true, value is {}
guardObject(p); // true, value is Person
```