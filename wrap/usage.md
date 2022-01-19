# Usage

### BBCode tag

Let's create a wrap for the BBCode tag.

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Let's create a BBCode wrap.
class BBCode<Name extends string> extends Wrap<`[`, Name, `]`> {
  constructor(name: Name) {
    super(`[`, `]`, name);
  }
}

// Make a [quote] BBCode tag. Returns BBCode {'[quote]'} of type BBCode<"quote">
const quoteTag = new BBCode('quote');

quoteTag.opening; // Returns [
quoteTag.closing; // Returns ]
quoteTag.text; // Returns quote
quoteTag.valueOf(); // Returns [quote]
quoteTag.getClosing();  // Returns [
quoteTag.getOpening(); // Returns ]
quoteTag.getText();  // Returns quote

// Make a [img] BBCode tag. Returns BBCode {'[img]'} of type BBCode<"img">
const imgTag = new BBCode('img');
```



### Html tag

Let's create a wrap for the HTML tag.

```typescript
// Example usage.
import { Wrap } from '@angular-package/wrapper';

// Let's create a Html wrap.
class Html<Name extends string> extends Wrap<`<`, Name, `>`> {
  constructor(name: Name) {
    super(`<`, `>`, name);
  }
}

// Make a <span> Html tag. Returns Html{'<span>'} of type Html<"span">
const spanTag = new Html('span');
spanTag.opening; // Returns <
spanTag.closing; // Returns >
spanTag.text; // Returns span
spanTag.valueOf(); // Returns <span>
spanTag.getClosing();  // Returns <
spanTag.getOpening(); // Returns >
spanTag.getText();  // Returns <span>

// Make a <img> Html tag. Returns Html{'<img>'} of type Html<"img">
const imgTag = new Html('img');
```
