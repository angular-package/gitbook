# Wrapped

## `Wrapped<`<mark style="color:green;">`Opening`</mark>`,`<mark style="color:green;">`Text`</mark>`,`<mark style="color:green;">`Closing`</mark>`>`

The `Wrapped` type indicates the text wrapped by the opening characters at the **beginning** and the closing characters at the **end** of the text. It's built from generic type variables in order [`Opening`](wrapped.md#openingextendsstring), [`Text`](wrapped.md#textextendsstring) and [`Closing`](wrapped.md#closingextendsstring) on the template `${Opening}${Text}${Closing}`.

{% code title="wrapped.type.ts" %}
```typescript
export type Wrapped<
  Opening extends string = '',
  Text extends string = '',
  Closing extends string = ''
> = `${Opening}${Text}${Closing}`;
```
{% endcode %}

### Generic type variables

#### <mark style="color:green;">`Opening`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)`=`<mark style="color:green;">`''`</mark>

A generic type variable determines the opening characters placed before the text on the template `${Opening}${Text}${Closing}`.

#### <mark style="color:green;">`Text`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)`=`<mark style="color:green;">`''`</mark>

A generic type variable determines the text between the opening and closing characters on the template `${Opening}${Text}${Closing}`.

#### <mark style="color:green;">`Closing`</mark>`extends`[<mark style="color:green;">`string`</mark>](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)`=`<mark style="color:green;">`''`</mark>

A generic type variable determines the closing characters placed after the text on the template `${Opening}${Text}${Closing}`.

### Returns

The type returns [template literal](https://www.typescriptlang.org/docs/handbook/2/template-literal-types.html) of generic type variables in order [`Opening`](wrapped.md#openingextendsstring), [`Text`](wrapped.md#textextendsstring) and [`Closing`](wrapped.md#closingextendsstring) indicating wrapped text.
