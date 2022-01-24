# isParam()

## `isParam()`

Method decorator to check the type and return `undefined` if it's not the same as expected.

```typescript
function isParam(...param: Array<string>): MethodDecorator {
  return (target: Function | object, key: string | symbol, descriptor: any): any => {
    const originalMethod = descriptor.value;

    descriptor.value =  function(): void {
      if (is.array(param) && is.defined(arguments)) {
        param.forEach((name: string, index: number) => {
          if (is.number(index) && index < arguments.length) {
            if (is.defined(arguments[index])) {
              switch (name) {
                case 'number':
                  if (is.number(arguments[index]) === false) {
                    arguments[index] = undefined;
                  }
                  break;
                case 'object':
                  if (is.object(arguments[index]) === false) {
                    arguments[index] = undefined;
                  }
                  break;
                case 'string':
                  if (is.string(arguments[index]) === false) {
                    arguments[index] = undefined;
                  }
                  break;
              }
            }
          }
        });
      }
      const result = originalMethod.apply(this, arguments);
      return result;
    };

    return descriptor;
  };
}
```

### Example usage

```typescript
// Example  usage
import { isParam } from '@angular-package/type';

const STRING: any = '!@#$%^&*()abcdefghijklmnoprstuwyz';
const NUMBER: any = 10304050;

// TestClass
class TestClass {
  @isParam('object', 'string', 'number')
  public testMethod(object?: any, firstName?: any, age?: any): { object: any, firstName: any, age: any } {
    return {object, firstName, age};
  }
}
const resultTRUE = new TestClass().testMethod({firstName: 'NoName'}, STRING, NUMBER);
const resultFALSE = new TestClass().testMethod(NUMBER, {firstName: 'NoName'}, STRING);

resultTRUE === {
  object: {firstName: 'NoName'},
  string: '!@#$%^&*()abcdefghijklmnoprstuwyz',
  number: 10304050
};

resultTRUE === {
  object: undefined,
  string: undefined,
  number: undefined
};

```
