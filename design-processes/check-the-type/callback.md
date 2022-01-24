# Callback

To handle the **result** of the check(before it returns) with an additional payload there is a callback function, so it is possible to, for example, send it to error tracker [sentry.io](https://sentry.io) or even to change the value of the result and then return.

The callback function passes the `result` of the check, the `value` that was checked, and `payload` with by default function name that performed the callback and some additional properties depends on the used function. Payload is changeable by the `payload` parameter of the parent function and also it's possible to add new properties through it.

The default callback function is used to return the result of the check.

## Default `resultCallback()`

Default function to handle `callback` of `ResultCallback` type.

```typescript
const resultCallback = (result: boolean): boolean => result;
```

### Parameters

#### `result: boolean`

A value of [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) type of the result of the check.

### Returns

The **return value** is a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Boolean) of the result from the check.

## Custom callback function

A custom function to handle the `callback`.

### Example usage

```typescript
// Example usage.
import { CallbackPayload } from '@angular-package/type';

const firstName = 'Artemis';
const additionalPayload = {
  id: 1,
  field: 'firstName',
  database: 'gods',
};

/*
  By default `callback` parameter of `isString()` function passes
  `name` and the provided `value` of `CallbackPayload` interface.
*/
const customCallback = (
  result: boolean,
  value: any,
  payload?: CallbackPayload & typeof additionalPayload
): boolean => {
  /*
    payload {
      value: 'Artemis',
      id: 1,
      field: 'firstName',
      database: 'gods'
    }
  */
  if (result === false) {
    if (payload) {
      // Send e.g. to sentry.io.
      throw new Error(`${payload.value} must be a string`);
    }
  }
  return result;
};

const stringResult = isString(firstName, customCallback, additionalPayload);

// TODO: Example usage
const customCallback = <
  Payload extends CallbackPayload<{ database?: string; id?: number }>
>(
  result: boolean,
  value: any,
  payload?: Payload
) => {
  return result;
};

isObject('x', customCallback, { database: '' });
```
