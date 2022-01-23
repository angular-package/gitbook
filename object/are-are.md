# are: Are {}

## `are: Are {}`

The `object` consists of `are` prefixed functions.

{% code title="are.object.ts" %}
```typescript
const are: Are = Object.freeze({
  bigint: areBigInt, // From the `5.0.0` version.
  boolean: areBoolean, // From the `5.0.0` version.
  date: areDate, // From the `5.0.0` version.
  defined: areDefined, // From the `5.0.0` version.
  false: areFalse, // From the `5.0.0` version.
  null: areNull, // From the `5.0.0` version.
  number: areNumber, // From the `5.0.0` version.
  regexp: areRegExp, // From the `5.0.0` version.
  string: areString,
  symbol: areSymbol, // From the `5.0.0` version.
  true: areTrue, // From the `5.0.0` version.
  undefined: areUndefined // From the `5.0.0` version.
});
```
{% endcode %}
