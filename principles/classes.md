# Classes

## Member ordering

{% embed url="https://github.com/typescript-eslint/typescript-eslint/blob/main/packages/eslint-plugin/docs/rules/member-ordering.md" %}

{% code title="tslint.json" %}
```json5
"member-ordering": [
  true,
  {
    "order": [
      "public-static-accessor",
      "protected-static-accessor",
      "private-static-accessor",

      "public-static-field",
      "protected-static-field",
      "private-static-field",

      "public-instance-accessor",
      "protected-instance-accessor",
      "private-instance-accessor",

      "public-instance-field",
      "protected-instance-field",
      "private-instance-field",

      "public-static-method",
      "protected-static-method",
      "private-static-method",

      "public-constructor",
      "protected-constructor",
      "private-constructor",

      "public-instance-method",
      "protected-instance-method",
      "private-instance-method"
    ]
  }
]
```
{% endcode %}

### Example class

```typescript
class MemberOrdering {

  public static get publicStaticGetAccessor(): void { return ; }
  public static set publicStaticGetAccessor(value: any) {  }

  protected static get protectedStaticGetAccessor(): void { return; }
  protected static set protectedStaticGetAccessor(value: any) {  }

  private static get privateStaticGetAccessor(): void { return; }
  private static set privateStaticGetAccessor(value: any) { }

  public static publicStaticProperty = '';
  protected static protectedStaticProperty: void;
  private static privateStaticProperty: void;

  public get publicGet(): void { return; }
  public set publicSet(value: any) { }

  public publicProperty: any;
  protected protectedProperty: any;
  private privateProperty: any;

  constructor() {}

  public publicMethod(): any { }
  protected protectedMethod(): any { }
  private privateMethod(): any { }
}
```
