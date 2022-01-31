# replaceOpeningIn()

## `Wrapper.prototype.replaceOpeningIn()`

Replaces the [`opening`](../../../wrap/accessors/#wrap.prototype.opening) chars of the [`Wrapper`](../../description.md) object in the given [`text`](replaceopeningin.md#text-string) with a given replacement [value](replaceopeningin.md#replacevalue-string).

{% hint style="info" %}
The replacement succeeds if the opening characters exist at the beginning of the text.
{% endhint %}

{% code title="wrapper.class.ts" %}
```typescript
public replaceOpeningIn(text: string, replaceValue: string): string {
  return Wrapper.replaceOpening(text, this.opening, replaceValue);
}
```
{% endcode %}

### Parameters

#### `text: string`

The text of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type in which the [`opening`](../../../wrap/accessors/#wrap.prototype.opening) chars are replaced by given replacement [value](replaceopeningin.md#replacevalue-string).

#### `replaceValue: string`

The value of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type as a replacement for the [`opening`](../../../wrap/accessors/#wrap.prototype.opening) chars at the **beginning** of the given [`text`](replaceopeningin.md#text-string).

### Returns

The **return value** is the text of [`string`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String) type with replaced [`opening`](../../../wrap/accessors/#wrap.prototype.opening) chars by given replacement [value](replaceopeningin.md#replacevalue-string).

## Example usage

```typescript
// Example usage.
import { Wrapper } from '@angular-package/wrapper';


```
