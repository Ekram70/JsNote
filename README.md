# Complete JavaScript Note

In this note we will discuss all JavaScript methods and properties including Dom, Web Api, Window, Bom & html element object.

## Table Of Contents

1. [Array Methods](#array)

<a name="array"></a>

## Array Methods

### Array.from()

---

#### Description

    creates a new, shallow-copied Array instance from an array-like or iterable object.

#### Syntax

```js
Array.from(arrayLike, mapFn, thisArg);
```

#### Parameter

    arrayLike = An array-like or iterable object to convert to an array.
    mapFn (Optional) = mapFn(element, index) - Map function to call on every element of the array. Index is optional.
    thisArg (Optional) = Value to use as this when executing mapFn.

#### Return value

    A new Array instance.

#### Example

```js
Array.from("foo");
// ["f", "o", "o"]
Array.from([1, 2, 3], (x) => x + x);
// [2, 4, 6]
Array.from(155);
// 155 is not iterable
// []
```

<br>

### Array.isArray()

---

#### Description

    determines whether the passed value is an Array.

#### Syntax

```js
Array.isArray(value);
```

#### Parameter

    value - The value to be checked.

#### Return value

    true if the value is an Array; otherwise, false.

#### Example

```js
Array.isArray(undefined);
// false
Array.isArray([1, 2, 3]);
// true
Array.isArray(Array.prototype);
// Array.prototype itself is an array:
// true
```

#### Special Note

    arr([1,2,3]) instanceof Array

    When checking for Array instance, Array.isArray is preferred over instanceof because it works through iframes.

<br>

### Array.of()

---

#### Description

    creates a new Array instance from a variable number of arguments, regardless of number or type of the arguments.

#### Syntax

```js
Array.of(element0, element1, /* ... ,*/ elementN);
```

#### Parameter

    element = Elements used to create the array.

#### Return value

    A new Array instance.

#### Example

```js
Array.of(7);
// [7]
Array(7);
// array of 7 empty slots
Array.of(1, 2, 3);
// [1, 2, 3]
Array(1, 2, 3);
// [1, 2, 3]
Array.of(undefined);
// [undefined]
Array.of();
// []
```

<br>

### Array.prototype.at()

---

#### Description

    takes an integer value and returns the item at that index, allowing for positive and negative integers. Negative integers count back from the last item in the array.

#### Syntax

```js
at(index);
```

#### Parameter

    index = The index (position) of the array element to be returned.

#### Return value

    The element in the array matching the given index. Returns undefined if the given index can not be found.

#### Example

```js
[10, 20, 50].at(1);
// 20
[10, 20, 50].at(-1);
// can be used instead of arr[arr.length-1]
// 50
[10, 20, 50].at();
// 10
[10, 20, 50].at(3);
// undefined
```

<br>

### Array.prototype.concat()

---

#### Description

    used to merge two or more arrays. This method does not change the existing arrays, but instead returns a new array.

#### Syntax

```js
concat(value0, value1, ... , valueN)
```

#### Parameter

    value (optional) = Arrays and/or values to concatenate into a new array. If all valueN parameters are omitted, concat returns a shallow copy of the existing array on which it is called.

#### Return value

    A new Array instance.

#### Example

```js
const num1 = [1, 2, 3];
const num2 = [4, 5, 6];
const num3 = [7, 8, 9];

num1.concat(num2, num3);
// [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

#### Special Note

    retention of references:
    const num1 = [[1]];
    const num2 = [2, [3]];
    const numbers = num1.concat(num2);
    console.log(numbers);
    // [[1], 2, [3]]

    num1[0].push(4);
    console.log(numbers);
    // [[1, 4], 2, [3]]

<br>

### Array.prototype.every()

---

#### Description

    tests whether all elements in the array pass the test implemented by the provided function. It returns a Boolean value.

#### Syntax

```js
every(callbackFn, thisArg);
```

#### Parameter

    callbackFn = function(element, index, array){} element is mandatory.
    thisArg (Optional) = A value to use as this when executing callbackFn.

#### Return value

    true if the callbackFn function returns a truthy value for every array element. Otherwise, false.

#### Example

```js
[12, 5, 8, 130, 44].every((x) => x >= 10);
// false
[12, 54, 18, 130, 44].every((x) => x >= 10);
// true
```

<br>

### ()

---

#### Description

    desc

#### Syntax

```js
syntax;
```

#### Parameter

    param =

#### Return value

    return

#### Example

```js
console.log(example);
```

#### Special Note

    note

<br>
