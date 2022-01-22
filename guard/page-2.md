# guardClass()

### `guard()`

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

A generic type variable `Class` constrained by [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) indicates the captured type of the given `value` via the [return type](page-2.md#return-type) and the `value` parameter of the provided callback function [`ResultCallback`](../types/resultcallback.md) type.

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by object indicates the type of the `payload` parameter of the main function from which it gets its value and callback function `payload` parameter.

### Parameters

#### `value: Class`

The [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global\_attributes/class) of a generic type variable [`Class`](page-2.md#classextendsfunction) to guard.

#### `callback: ResultCallback<Class, Payload>`

A callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../types/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](page-2.md#payloadextendsobject-object) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

Optional [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of generic type variable [`Payload`](page-2.md#payloadextendsobject-object) is assigned to the `payload` of the supplied `callback` function.

### Return type

#### `value is Class`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the `value` is a generic type variable [`Class`](page-2.md#classextendsfunction) by default of type captured from the supplied [`value`](page-2.md#value-class).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided [`value`](page-2.md#value-class) is a [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global\_attributes/class) of a generic type variable [`Class`](page-2.md#classextendsfunction).

### Example usage

```typescript
// Example usage.
import { guardClass } from '@angular-package/type';


```
