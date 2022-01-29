# v5.0.0

## \[5.0.0] - 2021-09-23

### Added

* Added `Undefined` generic type.
* Added guard function `guardStringLengthBetween()`. [53e02d8](https://github.com/angular-package/type/commit/53e02d8fdf33ef9c2a66615be19c22eb3a606b12)
* Added check function `isStringLengthBetween()`. [5d044f9](https://github.com/angular-package/type/commit/5d044f9a8a5dce0c3e79f6858b0e29a81cf3f3d5)
* Added generic type `GenericObject`. [fd14947](https://github.com/angular-package/type/commit/fd1494735a7ddf6653919448b67984cbb341bbdc)
* Added `guardStringIncludes()` and `guardStringIncludesSome()` functions with tests. [691f07e](https://github.com/angular-package/type/commit/691f07e2cf31eb3a52923715ef091f86a181a15f)
* Added `guardObjectKeysIn()` function to guard the value to be an `object` with specified keys in it(or its prototype chain). [21e523b](https://github.com/angular-package/type/commit/21e523b3a46e3e8243276e5008de72ea9b3c3756)
* Added `are` prefixed functions to check the values of a rest parameter. `areBigInt()` `areBoolean()` `areDate()` `areDefined()` `areFalse()` `areNull()` `areNumber()` `areRegExp()` `areSymbol()` `areTrue()` `areUndefined()`. [823dac3](https://github.com/angular-package/type/commit/823dac3b62288c1016e8244fc741939bdc140d89)
* Added a generic type `MinMax` that takes generic type variable `Min` and `Max` that represents the range between minimum and maximum. [e503d38](https://github.com/angular-package/type/commit/e503d3885d560274e1f30e763e04c526a8548317)
* Added new guard functions `guardDate()`, `guardFalse()`, `guardNumberBetween()`, `guardObjectKeyIn()`, `guardObjectSomeKeys()`, `guardRegExp()`, `guardStringLength()`, `guardTrue()`. [c374612](https://github.com/angular-package/type/commit/c374612e96d14c6d23449e03535283e5e1614765)
* Added `isObjectKeysIn()`, `isObjectSomeKeys()`, `isStringIncludes()` and `isStringIncludesSome()` and to the `is` object and to the `Is` interface. [55635fa](https://github.com/angular-package/type/commit/55635fad55a8f0e14486246215cf7f22b9f1ab26) [1e48fb1](https://github.com/angular-package/type/commit/1e48fb1448b908f09cc2628063eff457d920a903) [a4cb61d](https://github.com/angular-package/type/commit/a4cb61d5b8bfd7f1ac548842d355a045266f6e7b) [f809f32](https://github.com/angular-package/type/commit/f809f32cddd2c53568d60f0af6e57b941d50fa87) [5c85a03](https://github.com/angular-package/type/commit/5c85a03a7fd34dd64a650597f48cea9968940f68) [d440e38](https://github.com/angular-package/type/commit/d440e388f6f853c01ef9aab620c206f2233bd3cf) [0efe8ae](https://github.com/angular-package/type/commit/0efe8aed83d03313921176206636bc8b0730d188)
* Added `CallbackPayload` and `ForEachCallback` types. [98a2722](https://github.com/angular-package/type/commit/98a2722ea64ccb476942b606239dd001457d7e03)
* Added the `type` object consists of `are`, `is` and `guard` objects. [dfb3df9](https://github.com/angular-package/type/commit/dfb3df9f82116cd2737031b255f0aad62e4c1fa8)
* Added an object to handle executing the tests. [8dd8099](https://github.com/angular-package/type/commit/8dd80991ba9e5950970880d8aa449c1c7a143699) [230063b](https://github.com/angular-package/type/commit/230063ba135022fdcbbb65fc3569f248f836adbf)
* Added `recognizeValue()` to recognize type of any value. [d2f756e](https://github.com/angular-package/type/commit/d2f756e1498b531836aaac08a9c01b512cdaba2c)

### Changed

* Updated the way of checking values in some of the `is` and `guard` prefixed functions.
* Updated `isPrimitive()` and `isType()` function does not use switch on the `type` argument.
* Updated **`guard`**, **`is`**, **`isNot`** prefixed functions to use updated generic type **`ResultCallback`** with **`payload`** parameter of generic type variable `Payload`.
* Updated `isStringLength()` function to check the specific `length`. [061ab52](https://github.com/angular-package/type/commit/061ab521e29b046549f169d5c7ebdd5f8f9f24b6)
* Updated `guardStringLength()` function to check the specific `length`. [0e48591](https://github.com/angular-package/type/commit/0e485914cc410509efed0bcfa40d29c456fc9b32)
* Updated `is {}` object by adding `stringLengthBetween` method. [083ffd0](https://github.com/angular-package/type/commit/083ffd06832a2381dac4755f0b206eb81d8cc25a)
* Updated `guardIs` object by adding `objectKeysIn`, `stringIncludes`, `stringLengthBetween` and `stringIncludesSome` methods. [8679b4c](https://github.com/angular-package/type/commit/8679b4c5845880a3be41d6d72dd115a7f4d99be2) [1d44d2e](https://github.com/angular-package/type/commit/1d44d2eb3f69ca372486037bad06aa2feb59419f)
* Updated `GuardIs` interface by adding `stringLengthBetween`. [7387e23](https://github.com/angular-package/type/commit/7387e2342b7c02ccf64f8cb980cd8b801e333ca9)
* Updated `areString()` function that works by using the returned methods. [68c9365](https://github.com/angular-package/type/commit/68c93656d4b3cd1c5158bc6021059929e54860ab)
* Freeze the `guard`, `guardIs`, `isNot` and `is` object. [00e8841](https://github.com/angular-package/type/commit/00e8841cc63430ee6423232ee804196fee9cbfd5) [09fb70f](https://github.com/angular-package/type/commit/09fb70f87634923dce1fd979da30a8041a7f9922) [c4e6f8f](https://github.com/angular-package/type/commit/c4e6f8f033364b24fd864b77ab62c7de70d7c265) [0efe8ae](https://github.com/angular-package/type/commit/0efe8aed83d03313921176206636bc8b0730d188)
* Updated `isObject()` function by adding the ability to check any kind of object, not only the `Object`. [de6aa12](https://github.com/angular-package/type/commit/de6aa127ec3f0821487448d784d390edc35fb289)
* Updated `NumberBetween` interface by adding `MinMax` interface and a generic type variable `Type`. [1263a2e](https://github.com/angular-package/type/commit/1263a2e92f6722dd9d025f5c5eef0e1ba652fe66)
* Updated `StringOfLength` interface by adding `MinMax` interface and a generic type variable `Type`. [24621f7](https://github.com/angular-package/type/commit/24621f7b421392226e939161989b28ae0898524f)
* Updated `isInstance()` function can now check any kind of instance. [7d288c2](https://github.com/angular-package/type/commit/7d288c2290055a164259f6e5ea336bec8938bf66)
* Updated `Is` interface by adding `stringLengthBetween`. [26d7a9d](https://github.com/angular-package/type/commit/26d7a9d2dc5fd84e5715ccea679bf2412f57c45a) [8ddb720](https://github.com/angular-package/type/commit/8ddb720a071dc97ccfdda8757f911aac1a6ec9bd)
* Updated `Is` interface and `isNot` by changing the function types to the `typeof` operator. [8ddb720](https://github.com/angular-package/type/commit/8ddb720a071dc97ccfdda8757f911aac1a6ec9bd)
* Updated the type of callback function **`ResultCallback`** to provide the type of value and the shape of `payload`. [8ddb720](https://github.com/angular-package/type/commit/8ddb720a071dc97ccfdda8757f911aac1a6ec9bd) [34a1b1f](https://github.com/angular-package/type/commit/34a1b1fc0fac8b9044d3c4da96d9dc642f388507)
* Updated functions by adding a generic type variable **`Payload`** constrained by the `object` type that is by default equal to the `object`. [5c9486f](https://github.com/angular-package/type/commit/5c9486f859a4e61476c220f228bf1cb34511e319)
* Updated functions by adding a `payload` parameter of generic type ~~`CallbackPayload`~~ that takes generic type variable `Payload` to assign to callback function `payload` parameter. [6d190f5](https://github.com/angular-package/type/commit/6d190f5ef1d425b272ca65954e5a9780f561d3c6)
* Updated functions by removing `typeOf()` function if it's not necessary to use it. [8ddb720](https://github.com/angular-package/type/commit/8ddb720a071dc97ccfdda8757f911aac1a6ec9bd)
* Updated the `Defined` to not use of `Never` type cause of some compile issues. [e09a84f](https://github.com/angular-package/type/commit/e09a84fc1ea2109c4c480743e3b749325a1d9c5f)
* Updated the `guard` object by removing `is` property. [aa80250](https://github.com/angular-package/type/commit/aa80250dec231e10dc11d14c7b86e88c2297e82b)
* Updated the `isParam()` function by removing the `Func` generic type in favor of `Function`. [42065c9](https://github.com/angular-package/type/commit/42065c9f7aa938e2d514ff9bfc9b197463a9bbda)
* Updated `isObjectKey()`, `isObjectKeyIn` to check only one key instead of multiple keys. [b7092a9](https://github.com/angular-package/type/commit/b7092a9766c5706ba2c7ba5670a96553f1ad4bd0)
* Updated `isObjectKeys()` works differently, now it searches for every key. The previous functionality provides `isObjectSomeKeys()`. [b7092a9](https://github.com/angular-package/type/commit/b7092a9766c5706ba2c7ba5670a96553f1ad4bd0)

### Removed

* Removed `guard` prefixed function types. [a8e8566](https://github.com/angular-package/type/commit/a8e856663f8c57c3c89271c1c1948ecdc96b01d1)
* Removed `Func` type in favor of build-in `Function` type. [8ddb720](https://github.com/angular-package/type/commit/8ddb720a071dc97ccfdda8757f911aac1a6ec9bd) [5148f05](https://github.com/angular-package/type/commit/5148f059722ee8979d8cf1945f80d8e65290bb0d)
* Removed `Key` type in favor of build-in `PropertyKey` type. [562ec13](https://github.com/angular-package/type/commit/562ec1396f61bb8b1c7363097a5e8b9a2e4392bc)
* Removed `CycleHook` type. [4d53a55](https://github.com/angular-package/type/commit/4d53a55a6b26d8a20678ae3dc39544e24cd3d9fa)
