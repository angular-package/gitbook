# Wrapped

### `Wrapped<Opening, Text, Closing>`

The `Wrapped` type indicates the text wrapped by the opening characters at the beginning and the closing characters at the end of the text. It's built from generic type variables in order `Opening`, `Text` and `Closing` on the template `${Opening}${Text}${Closing}`.

```typescript
export type Wrapped<
  Opening extends string = '',
  Text extends string = '',
  Closing extends string = ''
> = `${Opening}${Text}${Closing}`;
```
