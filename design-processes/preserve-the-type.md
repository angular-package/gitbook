# Preserve the type

#### Date: 09.02.2022

Typescript generic type variables preserve the captured type of the given value resulting in having the exact type of this value. The following examples examine the generic type variables usage in different ways.&#x20;

First, let's see how the type is captured by simply assigning value to the constant.

## Assigning

### BigInt

```typescript
/*
    BigInt
*/
// 1n
const age = 1n;

// bigint
const moreAge: bigint = 2n;

// { age: bigint; }
const objectAge = { age: 1n };

// { age: bigint; }
const objectMoreAge = { age };
```

{% embed url="https://www.typescriptlang.org/play?jsx=0&target=7#code/PQKgsAUABDUEIEsDmBJAdgF0iYljCgEY1IBjAezQGcMoBDJAUygF4i0BuSPAgI2QSYylGlAC25AE6MAgkwBcUfkkG02AJk7cI+KAG96CpQMwcoAX2HVa5XgCtGpDHOZsDDRouIWuEHvsNPYxVTCytRWwcnAFkpWSZWAI8fSCA" %}

### Number

```typescript
/*
    Number
*/
// 27 
const someoneAge = 27;

// number[]
const ageInArray = [ 27 ];

// number[]
const someoneAgeInArray = [someoneAge];

// { age: number }
const ageInObject = { age: 27 };

// { someoneAge: number; }
const someoneAgeInObject = { someoneAge }
```

{% embed url="https://www.typescriptlang.org/play?jsx=0&target=7#code/PQKgsAUABDUHIFcC2AjApgJ0iYljCgCYB2KSAYwHsA7AZwBcpbKk0a0BBAczSgF4ixANyQ8BasnQYA2gF0KNBlACGPAJLUOGDMoCe-KNMFRZIiGKgTUmOQrqNmrdtzQatO-QOmO21Tj1NRCHwoAG8VHgAuS0lMKABfOyVVV2oAeRQAKzRyRgFwlOiSBLMLcJ9nKJjrDCEEpIcWX39UjOzcg3Kmyt5EiCA" %}

### String

```typescript
/*
    String
*/
// "Someone" 
const firstName = 'Someone';

// string[] 
const arrayOf = ['Someone'];

// { firstName: string; }
const objectSomeone = { firstName: 'Someone' };

// string[] 
const arrayOfString = [firstName];

// { firstName: string; }
const objectFirstName = { firstName };
```

{% embed url="https://www.typescriptlang.org/play?jsx=0&target=7#code/PQKgsAUABDUMoBcBOBLAdgc0iYljCgCI4B7AWwFMS0LCpIBjagZwSgDMUlWA5AQ0pQAvFADkpStQqiA3JDwFWqTAG0AuvQhM0rKHyRI+ATwDy7YVBXjyVGqLVyICqAG8OXXgIoAuKEvQYMlAAvowsbCQARgBWFAwIErYUFm6c3Aj8lL7WknYhjs7+qhphOmz6hqbsiMoYFippnpQO8hD4ru7pmT5+yAFBoVrhUFGx8QBiHhleKZ1NycGOQA" %}

### Conclusion

We can see that the value type is **not** captured in the [`array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) or [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object), and now let's see what the generic type variables can capture by using the [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function).

## Capturing

Capture the number in the [`array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) or [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object).

### Number

<mark style="color:green;">Successful</mark> capture from an [`array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) by using the function with the generic type variable `Age`.

```typescript
// 27
const age = 27;

// Create function to capture the age in the array.
const captureAgeFromArray = <Age extends number>(age: Age[]) => {
  return age;
};

// (4 | 5)[]
captureAgeFromArray([4, 5]);

// (9 | 27)[]
captureAgeFromArray([9, age]);
```

{% embed url="https://www.typescriptlang.org/play?jsx=0&pc=1&pln=1&ssc=1&ssl=14&target=7#code/PTAECYHYFgCgGMD2A7AzgF1AQwOYFNQBeCSAbjjhFAGEAnPLdAgMwFdl50BLFUdRUPCwAHdK3p8AFgVwEuyKTNq0sATwB0cJGkxDR4vAEF8AMVqIAtoeVqioADzGCeAB5NkAE1ShkrCwCM8WgA+AApZAC5QJwBtAF0ASiJg0ABvOFBQejFaBVlyWABfAsowUIAWUAAfUABWBPitERyjU3MrG1VQmPKAGjrEktgqUIBOapIGuKb9eiczS2sVLpjR-tlBuCA" %}

<mark style="color:red;">Unsuccessful</mark> capture from an [`array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) by using the function with the generic type variable `Age`.

```typescript
// 27
const age = 27;

// Create function to capture the age in the array.
const captureAgeFromArray = <Age extends number>(age: Age[]) => {
  return age;
};

// Define constant to provide to the function.
const fromArray = [4, 5];

// number[] <---- Not Captured.
captureAgeFromArray(fromArray);

// Define constant to provide to the function.
const fromArrayAge = [9, age];

// number[] <---- Not Captured.
captureAgeFromArray(fromArrayAge);
```

{% embed url="https://www.typescriptlang.org/play?jsx=0&target=7#code/PTAECYHYFgCgGMD2A7AzgF1AQwOYFNQBeCSAbjjhFAGEAnPLdAgMwFdl50BLFUdRUPCwAHdK3p8AFgVwEuyKTNq0sATwB0cJGkxDR4vAEF8AMVqIAtoeVqioADzGCeAB5NkAE1ShkrCwCM8WgA+AApZAC5QJwBtAF0ASiJg0ABvOFBQejFaBVlyWABfAsowABE8ZnkCbQwsZEx+UGFzADcuDwIm9GlQNg5uFE0EFAw+8ysbVTsYgBYAGlAAVjiS2CpfAKD4hwBafd3QADlETGoRHLwPYb1LpzNLaxVVUOYJp7UEtaoKquQa0boeqNAQtRDtTp8AQ9FjsTg8ZA3QHjR5TJwzACci1kqwo6zAm0CtB29gOhxOZwuBmuWip9Hu7ymr0ZzycXyAA" %}

<mark style="color:green;">Successful</mark> capture from an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) by using the function with the generic type variable `Age`.

```typescript
// 27
const age = 27;

// Create function to capture the age in the object.
const captureAgeFromObject = <Age extends number>(age: { age: Age[] }) => {
    return age;
}

// { age: (4 | 5)[]; }
captureAgeFromObject({
    age: [4, 5]
});

// { age: (9 | 27)[]; }
captureAgeFromObject({
    age: [9, age]
});
```

{% embed url="https://www.typescriptlang.org/play?jsx=0&target=7#code/PTAECYHYFgCgGMD2A7AzgF1AQwOYFNQBeCSAbjjhFAGEAnPLdAgMwFdl50BLFUdRUPCwAHdK3p8AFgVwEuyKQUQAjAFZ5OAOjhI0mIaPF4AgvgBitRAFsA8mo2ZiAHlME8ADybIAJqlDJWK2U8WgA+AApZAC5QAG9sfBjXAG0AXVAAXwBKIlC4uFBC0HoxWgVZclgMilgqeOjQcIAWUAAfUABWLLTSTJ0RUpNzS1t7TnDYgqKG5KaAGk7UuGzKyjB6xMaATjaSbtTe6oQBo1cLazt1ccnYIoS8GOSthdklqqzKoA" %}

<mark style="color:red;">Unsuccessful</mark> capture from an [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) by using the function with the generic type variable `Age`.

```typescript
// 27
const age = 27;

// Create function to capture the age in the object.
const captureAgeFromObject = <Age extends number>(age: { age: Age[] }) => {
    return age;
}

// Define constant to provide to the function.
const fromObject = {
    age: [4, 5]
};

// { age: number[]; } <---- Not Captured.
captureAgeFromObject(fromObject);

// Define constant to provide to the function.
const fromObjectAge = {
    age: [9, age]
};

// { age: number[]; } <---- Not Captured.
captureAgeFromObject(fromObjectAge);
```

{% embed url="https://www.typescriptlang.org/play?jsx=0&target=7#code/PTAECYHYFgCgGMD2A7AzgF1AQwOYFNQBeCSAbjjhFAGEAnPLdAgMwFdl50BLFUdRUPCwAHdK3p8AFgVwEuyKQUQAjAFZ5OAOjhI0mIaPF4AgvgBitRAFsA8mo2ZiAHlME8ADybIAJqlDJWK2U8WgA+AApZAC5QAG9sfBjXAG0AXVAAXwBKIlC4uFBC0HoxWgVZclgMilgqABE8ZnkCXQwsZEx+UGFLADcubwIu9GlQNg5uFG0EFAwxy1t7TiJ82CKEvBjkgBYAGlAAVlS4DMrKMHjo-0Dg2jTSTNAnAFpX59AAOURMahFSvG80wM-1cFmsdnUnHCzAWEIcWTOtTADSayBas3Q7U6Ah6iH6gz4AhGLHYnB4yCBGPm4KW6FcK1iBSKV2SAE59rJjlVEVRLolrkEQvdHi83p9vjQ-kZATopfRQbDadDFZC6fgEXAgA" %}

### Conclusion

The [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function) with the generic type variable can capture the parameter type of [`array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array) or [`object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object) directly inputted, but through constant does not work. The same refers to the [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global\_attributes/class), getting the detailed/exact type of it.
