# Wrapped

## `Wrapped<Opening, Text, Closing>`

The `Wrapped` type indicates the text wrapped by the opening characters at the **beginning** and the closing characters at the **end** of the text. It's built from generic type variables in order `Opening`, `Text` and `Closing` on the template `${Opening}${Text}${Closing}`.

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

#### <mark style="color:green;">`Opening`</mark>`extends`<mark style="color:green;">`string`</mark>`=`<mark style="color:green;">`''`</mark>

asdasdasdasd

#### <mark style="color:green;">`Text`</mark>`extends`<mark style="color:green;">`string`</mark>`=`<mark style="color:green;">`''`</mark>

asdasdasd

#### <mark style="color:green;">`Closing`</mark>`extends`<mark style="color:green;">`string`</mark>`=`<mark style="color:green;">`''`</mark>

asdasdasdasd

### Return type

#### `${Opening}${Text}${Closing}`

asdasdasd

### Returns

asdasdasd
