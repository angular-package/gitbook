---
description: The `RangeErrors` object example usage
---

# Example usage

```typescript
// Example usage.
import { RangeErrors } from '@angular-package/error';

// Define range errors.
const rangeErrors = new RangeErrors('(RE: 4332)', '(RE: 4331)', '(RE: 4330)');
```

### `set()`

```typescript
// Set the `RangeError` objects under the given identification numbers.
rangeErrors
  .set('Age is 99', 'Age must be ', '(RE: 4330)', 9, 27)
  .set('Height can not be 11000', 'Set height ', '(RE: 4331)', 1, 1000)
  .set('Width can not be 300', 'Set width ', '(RE: 4331)', 1080, 1920);
```

### `delete()`

```typescript
// Example `delete()` method usage.
rangeErrors.delete('(RE: 4332)');
```

### `get()`

```typescript
// Example `get()` usage.

// Returns `undefined`.
rangeErrors.get('(RE: 4332)');

// Returns
// RangeError: Problem(RE: 4331): Width can not be 300 => Fix: Set width  between 1080 and 1920
rangeErrors.get('(RE: 4331)');
```

### `has()`

```typescript
// Example `has()` usage.

// Returns `false`.
rangeErrors.has('(RE: 4332)');

// Returns `true`.
rangeErrors.has('(RE: 4331)');
```

### `throw()`

```typescript
// Example `throw()` usage.
try {
  rangeErrors.throw('(RE: 4330)');
} catch (e) {
  if (RangeError.isRangeError(e)) {
    e.fix; // Age must be
    e.message; // Problem(RE: 4330): Age is 99 => Fix: Age must be  between 9 and 27
    e.name; // RangeError
    e.problem; // Age is 99
    e.template; // Problem{id}: {problem} => Fix: {fix} between {min} and {max}
    e.id; // (RE: 4330)
  }
}
```
