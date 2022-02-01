# Example usage

## `HtmlWrap`

Let's create a new `HtmlWrap` object extending it with the `Wrapper` to make an immutable `<span>` tag.

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';
 
// Define HtmlWrap class.
class HtmlWrap extends Wrapper<`<`, `>`> {
  constructor() {
    super(`<`, `>`);
  }
}

// Create the html tag '<span>'.
new HtmlWrap().wrap(`span`);
```

## `OfType`

Create a  new object `OfType` to make an immutable string indicating of type `: Opening`.

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';

class OfType extends String {
  constructor(name: string) {
    super(new Wrapper<`:`, ``>(`:`, ``).wrap(` ${name}`));
  }
}

// Returns OfType{': Opening'}.
const ofOpening = new OfType(`Opening`);

// Returns ': Opening'.
ofOpening.valueOf();
```
