# ForEachCallback

## `ForEachCallback<Value, Payload>`

Represents a callback function of `.forEach()` method which is executed **once** for each element.

{% code title="foreach-callback.type.ts" %}
```typescript
type ForEachCallback<Value = any, Payload = object> = (
  result: boolean,
  value: Value,
  index?: number,
  array?: any[],
  payload?: Payload
) => void;
```
{% endcode %}

{% embed url="https://github.com/angular-package/type/blob/main/src/type/foreach-callback.type.ts" %}

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`=`<mark style="color:green;">`any`</mark>

A generic type variable `Value` determines the type of the [`value`](foreachcallback.md#value-value) parameter, by default [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any).

#### <mark style="color:green;">`Payload`</mark>`=`<mark style="color:green;">`object`</mark>

The shape of the optional [`payload`](foreachcallback.md#payload-payload) parameter, by default [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object).

### Parameters

#### `result: boolean`

The result of the check of a [`boolean`](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean) type.

#### `value: Value`

The **value** that has been checked of a generic type variable [`Value`](foreachcallback.md#value-any).

#### `index: number`

An optional [`number`](https://www.typescriptlang.org/docs/handbook/basic-types.html#number) of checked `array` element.

#### `array: any[]`

An optional `array` of [`any`](https://www.typescriptlang.org/docs/handbook/basic-types.html#any) type that **each** element is checked.

#### `payload?: Payload`

An optional [`object`](https://www.typescriptlang.org/docs/handbook/basic-types.html#object) of a generic type variable [`Payload`](foreachcallback.md#payload-object) to provide more data.

### Return type

The return value is void.
