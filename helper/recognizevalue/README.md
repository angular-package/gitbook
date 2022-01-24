# recognizeValue()

## `recognizeValue()`

Gets recognized types and instances of given [`value`](./#value-any).

{% code title="recognize-value.func.ts" %}
```typescript
const recognizeValue = (
  value: any,
  onlyTrue: boolean = true,
  instances: any[] = []
): OfRecognized => {
  // Recognize types.
  const ofRecognized: OfRecognized = {
    'Array.isArray': Array.isArray(value),
    isClass: is.class(value),
    isFunction: is.function(value),
    'Number.isInteger': Number.isInteger(value),
    'Number.isFinite': Number.isFinite(value),
    'Number.isNaN': Number.isNaN(value),
    'Number.isSafeInteger': Number.isSafeInteger(value),
    typeOf: typeOf(value),
    typeof: typeof value,
  };

  try { Object.assign(ofRecognized, { isFinite: isFinite(value) }); } catch (e) {}
  try { Object.assign(ofRecognized, { isNaN: isNaN(value) }); } catch (e) {}

  // Recognize instances.
  RECOGNIZE_INSTANCES.concat(instances as any).forEach((instance) => (
    Object.assign(ofRecognized, { [instance.name]: value instanceof instance })
  ));

  // If only true remove false.
  if (is.true(onlyTrue)) {
    Object.keys(ofRecognized).filter((type: string) =>
      is.false(ofRecognized[type as keyof OfRecognized])
        ? delete ofRecognized[type as keyof OfRecognized]
        : true
    );
  }
  return ofRecognized;
};
```
{% endcode %}

### Parameters

#### `value: any`

The `value` of any type to recognize.

#### `onlyTrue: boolean`

Determines whether to show only recognized as `true`.

#### `instances: any[]`

An optional array of objects to check by using [`instanceof`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof) operator.

### Return type

#### `OfRecognized`

The **return type** is an interface of the operators and functions used to check.

### Returns

The **return value** is an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) of types and instances recognized as `true` or all even those recognized as `false`.

### Example usage

```typescript
// Example usage.
import { recognizeValue } from '@angular-package/type';

// Class.
class CustomClass {}
const customClass = new CustomClass();

// String.
const firstName = 'Artemis';


/*
Returns {
  "typeOf": "object",
  "typeof": "object",
  "isNaN": true,
  "Object": true,
  "CustomClass": true
}
*/
recognizeValue(customClass, true, [CustomClass]);

/*
Returns {
  "isClass": true,
  "typeOf": "function",
  "typeof": "function",
  "isNaN": true,
  "Function": true,
  "Object": true
}
*/
recognizeValue(CustomClass);

/*
Returns {
  "typeOf": "string",
  "typeof": "string",
  "isNaN": true
}
*/
recognizeValue(firstName);

/*
Returns {
  "typeOf": "string",
  "typeof": "object",
  "isNaN": true,
  "Object": true,
  "String": true
}
*/
recognizeValue(new String(firstName));
```
