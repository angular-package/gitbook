# isClass()

### `isClass()`

Checks if [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) value is a `function` type or of the type obtained from its `Object.prototype` equal to `'function'` and an instance of [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions). It also confirms it's a `class` by using `regexp` on the obtained string from its `Function.prototype`.

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

### Generic type variables

#### <mark style="color:green;">**`Class`**</mark>**`=`**<mark style="color:green;">**`Function`**</mark>

The `Class` generic type variable indicates the class type of the given `value` via the [return type](isclass.md#return-type).

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>**`=`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by object indicates the type of the `payload` parameter of the main function from which it gets its value and callback function `payload` parameter.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to check.

#### `callback: ResultCallback<any, Payload>`

A callback [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) of [`ResultCallback`](../type/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable [`Payload`](isclass.md#payloadextendsobject-object) with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

Optional `object` of generic type variable `Payload` is assigned to the `payload` of the supplied `callback` function.

### Return type

#### `value is Class`

The **return type** is a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) as the result of its statement indicating the `value` is a generic type variable [`Class`](isclass.md#class-function) by default equal to [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions).

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) indicating whether the provided `value` is a `class`.

### Example usage

```typescript
// Example usage.
import { isClass } from '@angular-package/type';

class Class { x = 5; }
const FUNC = (x: number): any => x + 5;

isClass<Class>(Class); // Returns `true` as `value is Class`
isClass(FUNC); // Returns `false` as `value is Function`
isClass(() => 5); // Returns `false` as `value is Function`

// Example usage with callback and payload.
isClass(() => 5, (result, value, payload) => {
  value // Returns `() => 5`
  if (payload) {
    result // Returns `false`
    payload.c // Returns `class Class`
  }
  return result;
}, { c: Class }); // Returns `false` as `value is Function`
```
