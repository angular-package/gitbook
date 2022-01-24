# CallbackPayload

## `CallbackPayload`

Experimental shape for a generic type variable `Payload`.

{% code title="callback-payload.type.ts" %}
```typescript
type CallbackPayload<Payload = object> = GenericObject & {
  action?: string;
  name?: string;
  param?: string;
} & Payload;
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Payload`</mark>`=`<mark style="color:green;">`object`</mark>

The shape of the optional `payload` parameter, by default equal to the \[`object`]\[js-object].

### Properties

#### `action?: string`

An optional action of a `string` type that describes the cause of performed callback.

#### `name?: string`

An optional name of the function or method of a `string` type that performed callback.

#### `param?: string`

An optional name of the parameter of a `string` type to which performed callback relates.

### Example usage

```typescript
// Example usage.
import { CallbackPayload, ResultCallback } from '@angular-package/callback';

// Create a new function.
const isString = (
  value: any,

  // Parameter callback of `ResultCallback` type with the `CallbackPayload`.
  callback: ResultCallback<any, CallbackPayload>
): any => {
  callback(typeof value === 'string', {
    // Property from the `CallbackPayload`.
    action: 'Checks the string of a firstName',

    // Property from the `CallbackPayload`.
    name: 'isString',

    // Property from the `CallbackPayload`.
    param: 'value',

    // Custom property.
    firstName: 'my Name',
  });
};

// The use of the `isString()` function.
isString('it is a string', (result: boolean, value, payload) => {
  if (payload !== undefined) {
    /*
    Returns {
      action: "Checks the string of a firstName",
      firstName: "my Name",
      name: "isString",
      param: "value",
    }
    */
    console.log(payload);
  }
  return result;
});
```
