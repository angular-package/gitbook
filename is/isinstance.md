# isInstance()

### `isInstance()`

Checks if any value is an instance of a given constructor.

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

#### <mark style="color:green;">**`Payload`**</mark>**`extends`**<mark style="color:green;">**`object`**</mark>

The `Payload` generic type variable constrained by [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) indicates the type of the `payload` parameter of the main function from which it gets its value and `payload` parameter of a given `callback` function [`ResultCallback`](../type/resultcallback.md) type.

### Parameters

#### `value: any`

The value of [`any`](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#any) type to be an instance of a given `constructor`.

#### `constructor: Constructor<Obj>`

A [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global\_attributes/class) or [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) that specifies the type of [`Constructor`](../type/constructor.md).

#### `callback: ResultCallback<any, Payload>`

A callback `function` of [`ResultCallback`](../type/resultcallback.md) type with parameters, the `value` that has been checked, the `result` of this check, and `payload` of generic type variable `Payload` with optional properties from the provided `payload`, to handle them before the `result` return. By default, it uses `resultCallback()` function.

#### `payload?: Payload`

Optional `object` of generic type variable [`Payload`](isinstance.md#payloadextendsobject) is assigned to the `payload` of the supplied `callback` function.

### Return type

### Returns

### Example usage

```typescript
// Example usage
import { isInstance } from '@angular-package/type';

```

