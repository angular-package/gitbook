# ForEachCallback

### `ForEachCallback<Value, Payload>`

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

### Generic type variables

#### <mark style="color:green;">`Value`</mark>`=`<mark style="color:green;">`any`</mark>

A generic type variable `Value` by default equal to `any` determines the type of the `value` parameter.

#### <mark style="color:green;">`Payload`</mark>`=`<mark style="color:green;">`object`</mark>

The shape of the optional `payload` parameter, by default equal to the \[`object`]\[js-object].

### Parameters

#### `result: boolean`

The result of the check of a `boolean` type.

#### `value: Value`

The **value** that has been checked of a generic type variable `Value`.

#### `index: number`

An optional `number` of checked `array` element.

#### `array: any[]`

An optional `array` of `any` type that **each** element is checked.

#### `payload?: Payload`

An optional `object` of a generic type variable `Payload` to provide more data.

### Return type

The return value is void.
