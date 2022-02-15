# Example usage

### `set()`

```typescript
// Example usage.
import { Errors } from '@angular-package/error';

// Define general errors.
const generalErrors = new Errors('(GE:021)', '(GE:022)', '(GE:027)');

// Set the `Error` objects under the given identification numbers.
generalErrors
  .set('Bad parameter', 'Provide the `install` parameter', '(GE:021)')
  .set('Bad function', 'Provide the function', '(GE:022)')
  .set('Wrong title', 'Provide only letters', '(GE:027)');
```

### `delete()`

```typescript
// Example `delete()` method usage.
generalErrors.delete('(GE:022)');
```

### `get()`

```typescript
// Example `get()` usage.

// Returns `undefined`.
generalErrors.get('(GE:022)');

// Returns Error: Problem(GE:027): Wrong title => Fix: Provide only letters
generalErrors.get('(GE:027)'); 
```

### `has()`

```typescript
// Example `has()` usage.

// Returns `false`.
generalErrors.has('(GE:022)');

// Returns `true`.
generalErrors.has('(GE:027)'); 
```

### `throw()`

```typescript
// Example `throw()` usage.

// Uncaught Error: Problem(GE:027): Wrong title => Fix: Provide only letters
generalErrors.has('(GE:027)'); 
```
