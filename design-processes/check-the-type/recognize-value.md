# Recognize value

To determine any value is to know what type and instance the value can be, when and what function or operators to use, and for this purpose `recognizeValue()` function was created, and it's not enough because it must be known what are the risks of using them.



Gets recognized types and instances of given `value` by using:



#### Function:

* `isClass()`,
* `isFinite()`,
* `isFunction()`,
* `isNaN()`,
* `typeOf()`,

#### Method:

* `Array.isArray`,
* `Number.isInteger()`,
* `Number.isFinite()`,
* `Number.isNaN()`,
* `Number.isSafeInteger()`,
* `Object.hasOwnProperty()`

#### Operator:

* \[`in`]\[js-in-operator] operator,
* \[`instanceof`]\[js-instanceof] operator,
* \[`typeof`]\[js-typeof] operator,



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
