# Complete JavaScript Note

In this note we will discuss all JavaScript methods and properties including Dom, Web Api, Window, Bom & html element object.

## Table Of Contents

1. [Array Methods](#array)
   1. [Array.from()](#arrayFrom)
   1. [Array.isArray()](#arrayIsArray)
   1. [Array.of()](#arrayOf)
   1. [Array.prototype.at()](#arrayAt)
   1. [Array.prototype.concat()](#arrayConcat)
   1. [Array.prototype.every()](#arrayEvery)
   1. [Array.prototype.fill()](#arrayFill)
   1. [Array.prototype.filter()](#arrayFilter)
   1. [Array.prototype.find()](#arrayFind)
   1. [Array.prototype.findIndex()](#arrayFindIndex)
   1. [Array.prototype.findLastIndex()](#arrayFindLastIndex)
   1. [Array.prototype.findLast()](#arrayFindLast)
   1. [Array.prototype.flat()](#arrayFlat)
   1. [Array.prototype.flatMap()](#arrayFlatMap)
   1. [Array.prototype.forEach()](#arrayForEach)
   1. [Array.prototype.includes()](#arrayIncludes)
   1. [Array.prototype.indexOf()](#arrayIndexOf)
   1. [Array.prototype.join()](#arrayJoin)
   1. [Array.prototype.lastIndexOf()](#arrayLastIndexOf)
   1. [Array.prototype.map()](#arrayMap)
   1. [Array.prototype.pop()](#arrayPop)
   1. [Array.prototype.push()](#arrayPush)
   1. [Array.prototype.reduce()](#arrayReduce)
   1. [Array.prototype.reduceRight()](#arrayReduceRight)
   1. [Array.prototype.reverse()](#arrayReverse)
   1. [Array.prototype.shift()](#arrayShift)
   1. [Array.prototype.slice()](#arraySlice)
   1. [Array.prototype.some()](#arraySome)
   1. [Array.prototype.sort()](#arraySort)
   1. [Array.prototype.splice()](#arraySplice)
   1. [Array.prototype.toString()](#arrayToString)
   1. [Array.prototype.unshift()](#arrayUnshift)

<a name="array"></a>

## Array Methods

<a name="arrayFrom"></a>

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

<a name="arrayIsArray"></a>

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

<a name="arrayOf"></a>

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

<a name="arrayAt"></a>

### Array.prototype.at() - Experimental

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

<a name="arrayConcat"></a>

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

<a name="arrayEvery"></a>

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

<a name="arrayFill"></a>

### Array.prototype.fill()

---

#### Description

    changes all elements in an array to a static value, from a start index (default 0) to an end index (default array.length). It returns the modified array.

#### Syntax

```js
fill(value, start, end);
```

#### Parameter

    value = Value to fill the array with. All elements in the array will be this exact value
    start (optional) = Start index (inclusive), default 0. accepts negative index value.
    end (optional) = End index (exclusive), default arr.length. accepts negative index value.

#### Return value

    The modified array, filled with value.

#### Example

```js
const array1 = [1, 2, 3, 4];

console.log(array1.fill(6));
//[6, 6, 6, 6]
console.log(array1.fill(5, 1));
//[1, 5, 5, 5]
console.log(array1.fill(0, 2, 4));
//[1, 2, 0, 0]
```

#### Special Note

    [1, 2, 3].fill(4, 1, 1)          // [1, 2, 3]
    [1, 2, 3].fill(4, NaN, NaN)      // [1, 2, 3]
    Array(3).fill(4)                 // [4, 4, 4]

<br>

<a name="arrayFilter"></a>

### Array.prototype.filter()

---

#### Description

    creates a new array with all elements that pass the test implemented by the provided function.

#### Syntax

```js
filter(callbackFn, thisArg);
```

#### Parameter

    callbackFn = function(element, index, array){}. This returns a value that coerces to true to keep the element, or to false otherwise.
    thisArg (optional) = Value to use as this when executing callbackFn.

#### Return value

    A new array with the elements that pass the test. If no elements pass the test, an empty array will be returned.

#### Example

```js
const arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
const filter = arr.filter((number) => number > 5);
console.log(filter); // [6, 7, 8, 9]
```

<br>

<a name="arrayFind"></a>

### Array.prototype.find()

---

#### Description

    returns the first element in the provided array that satisfies the provided testing function. If no values satisfy the testing function, undefined is returned.

#### Syntax

```js
find(callbackFn, thisArg);
```

#### Parameter

    callbackFn = function(element, index, array){}. Function to execute on each value in the array.
    thisArg (optional) = Value to use as this when executing callbackFn.

#### Return value

    The first element in the array that satisfies the provided testing function. Otherwise, undefined is returned.

#### Example

```js
const array1 = [5, 12, 8, 130, 44];
const found = array1.find((element) => element > 10);
console.log(found); // 12
```

<br>

<a name="arrayFindIndex"></a>

### Array.prototype.findIndex()

---

#### Description

     returns the index of the first element in the array that satisfies the provided testing function. Otherwise, it returns -1, indicating that no element passed the test.

#### Syntax

```js
findIndex(callbackFn, thisArg);
```

#### Parameter

    callbackFn = function(element, index, array){}. A function to execute on each value in the array until the function returns true, indicating that the satisfying element was found.
    thisArg (optional) = Value to use as this when executing callbackFn.

#### Return value

    The index of the first element in the array that passes the test. Otherwise, -1.

#### Example

```js
const arr = ["A", "B", "C"];
const index = arr.findIndex((item) => item === "B");
// index == 1
```

<br>

<a name="arrayFindLastIndex"></a>

### Array.prototype.findLastIndex()

---

#### Description

    It is opposite of Array.prototype.findIndex()

<br>

<a name="arrayFindLast"></a>

### Array.prototype.findLast()

---

#### Description

    It is opposite of Array.prototype.find()

<br>

<a name="arrayFlat"></a>

### Array.prototype.flat()

---

#### Description

    creates a new array with all sub-array elements concatenated into it recursively up to the specified depth.

#### Syntax

```js
flat(depth);
```

#### Parameter

    depth (optional) = The depth level specifying how deep a nested array structure should be flattened. Defaults to 1.

#### Return value

    A new array with the sub-array elements concatenated into it.

#### Example

```js
const arr1 = [1, 2, [3, 4]];
arr1.flat();
// [1, 2, 3, 4]

const arr4 = [1, 2, [3, 4, [5, 6, [7, 8, [9, 10]]]]];
arr4.flat(Infinity);
// [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

#### Special Note

    The flat method removes empty slots in arrays:
    const arr5 = [1, 2, , 4, 5];

    arr5.flat();
    // [1, 2, 4, 5]

<br>

<a name="arrayFlatMap"></a>

### Array.prototype.flatMap()

---

#### Description

    It is identical to a map() followed by a flat() of depth 1,

<br>

<a name="arrayForEach"></a>

### Array.prototype.forEach()

---

#### Description

    executes a provided function once for each array element.

#### Syntax

```js
forEach(callbackFn, thisArg);
```

#### Parameter

    callbackFn = function(element, index, array){}. Function to execute on each element.

#### Return value

    undefined.

#### Example

```js
const array1 = ["a", "b", "c"];
array1.forEach((element) => console.log(element));
//"a" //"b" //"c"
```

#### Special Note

    forEach() is not chainable as it returns undefined.

<br>

<a name="arrayIncludes"></a>

### Array.prototype.includes()

---

#### Description

    determines whether an array includes a certain value among its entries, returning true or false as appropriate. It only searches from the specified index to right side.

#### Syntax

```js
includes(searchElement, fromIndex);
```

#### Parameter

    searchElement = The value to search for. When comparing strings and characters, includes() is case-sensitive.
    fromIndex (optional) = The position in this array at which to begin searching for searchElement. Accept negative index values. Defaults to 0.

#### Return value

    A boolean value which is true if the value searchElement is found within the array (or the part of the array indicated by the index fromIndex, if specified).

#### Example

```js
[1, 2, 3].includes(3, -1); // true
[1, 2, NaN].includes(NaN); // true
["1", "2", "3"].includes(3); // false
```

#### Special Note

    let arr = ['a', 'b', 'c']
    arr.includes('c', 100) // false
    arr.includes('a', -100) // true

<br>

<a name="arrayIndexOf"></a>

### Array.prototype.indexOf()

---

#### Description

    returns the first index at which a given element can be found in the array, or -1 if it is not present.

#### Syntax

```js
indexOf(searchElement, fromIndex);
```

#### Parameter

    searchElement = Element to locate in the array.
    fromIndex (optional) = The index to start the search at. Accept negative index values. Defaults to 0.

#### Return value

    The first index of the element in the array; -1 if not found.

#### Example

```js
const beasts = ["ant", "bison", "camel", "duck", "bison"];
console.log(beasts.indexOf("bison"));
// 1
console.log(beasts.indexOf("bison", 2));
//4
console.log(beasts.indexOf("giraffe"));
//-1

const array = [2, 9, 9];
console.log(array.indexOf(9, 10));
// -1;
```

#### Special Note

    indexOf() compares searchElement to elements of the Array using strict equality (the same method used by the === or triple-equals operator).

<br>

<a name="arrayJoin"></a>

### Array.prototype.join()

---

#### Description

    creates and returns a new string by concatenating all of the elements in an array (or an array-like object), separated by commas or a specified separator string. If the array has only one item, then that item will be returned without using the separator.

#### Syntax

```js
join(separator);
```

#### Parameter

    separator (optional) = Specifies a string to separate each pair of adjacent elements of the array. The separator is converted to a string if necessary. If omitted, the array elements are separated with a comma (","). If separator is an empty string, all elements are joined without any characters in between them.

#### Return value

    A string with all array elements joined. If arr.length is 0, the empty string is returned.

#### Example

```js
const elements = ["Fire", "Air", "Water"];
console.log(elements.join());
//"Fire,Air,Water"
console.log(elements.join(""));
//"FireAirWater"
console.log(elements.join("-"));
//"Fire-Air-Water"
```

#### Special Note

    If an element is undefined, null or an empty array [], it is converted to an empty string.

<br>

<a name="arrayLastIndexOf"></a>

### Array.prototype.lastIndexOf()

---

#### Description

    It is opposite of Array.prototype.indexOf()

<a name="arrayMap"></a>

### Array.prototype.map()

---

#### Description

    creates a new array populated with the results of calling a provided function on every element in the calling array.

#### Syntax

```js
map(callbackFn, thisArg);
```

#### Parameter

    callbackFn = function(element, index, array){}. Function that is called for every element of arr

#### Return value

    A new array with each element being the result of the callback function

#### Example

```js
const array1 = [1, 4, 9, 16];
const map1 = array1.map((x) => x * 2);
console.log(map1);
// [2, 8, 18, 32]
```

#### Special Note

    It is not called for missing elements of the array; that is:
    indexes that have never been set;
    indexes which have been deleted.

    You shouldn't be using map if:
    you're not using the array it returns; and/or
    you're not returning a value from the callback.

    Mapped array contains undefined
    When undefined or nothing is returned.

<br>

<a name="arrayPop"></a>

### Array.prototype.pop()

---

#### Description

    removes the last element from an array and returns that element. This method changes the length of the array.

#### Syntax

```js
pop();
```

#### Return value

    The removed element from the array; undefined if the array is empty.

#### Example

```js
const plants = ["broccoli", "cauliflower", "cabbage"];
console.log(plants.pop());
// "cabbage"
console.log(plants);
// ["broccoli", "cauliflower"]
```

<br>

<a name="arrayPush"></a>

### Array.prototype.push()

---

#### Description

    adds one or more elements to the end of an array and returns the new length of the array.

#### Syntax

```js
push(element0, element1, /* ... ,*/ elementN);
```

#### Parameter

    elementN = The element(s) to add to the end of the array.

#### Return value

    The new length property of the object upon which the method was called.

#### Example

```js
const animals = ["pigs", "goats", "sheep"];
const count = animals.push("cows");
console.log(count);
// 4
console.log(animals);
// ["pigs", "goats", "sheep", "cows"]
```

<br>

<a name="arrayReduce"></a>

### Array.prototype.reduce()

---

#### Description

    executes a user-supplied "reducer" callback function on each element of the array, in order, passing in the return value from the calculation on the preceding element. The final result of running the reducer across all elements of the array is a single value.

    The first time that the callback is run there is no "return value of the previous calculation". If supplied, an initial value may be used in its place. Otherwise the array element at index 0 is used as the initial value and iteration starts from the next element (index 1 instead of index 0).

#### Syntax

```js
reduce(callbackFn, initialValue);
```

#### Parameter

    callbackFn = function(previousValue, currentValue, currentIndex, array){}
    previousValue = the value resulting from the previous call to callbackFn. On first call, initialValue if specified, otherwise the value of array[0].
    currentValue (optional) = the value of the current element. On first call, the value of array[0] if an initialValue was specified, otherwise the value of array[1].
    currentIndex (optional) = the index position of currentValue in the array. On first call, 0 if initialValue was specified, otherwise 1.

    initialValue (optional) = A value to which previousValue is initialized the first time the callback is called. If initialValue is specified, that also causes currentValue to be initialized to the first value in the array. If initialValue is not specified, previousValue is initialized to the first value in the array, and currentValue is initialized to the second value in the array.

#### Return value

    The value that results from running the "reducer" callback function to completion over the entire array.

#### Example

```js
let flattened = [
  [0, 1],
  [2, 3],
  [4, 5],
].reduce(function (previousValue, currentValue) {
  return previousValue.concat(currentValue);
}, []);
// [0, 1, 2, 3, 4, 5]
```

#### Special Note

    // callback is not invoked
    [ 50].reduce(getMax); // 50
    [ ].reduce(getMax, 1); // 1

<br>

<a name="arrayReduceRight"></a>

### Array.prototype.reduceRight()

---

#### Description

    The reduceRight() method applies a function against an accumulator and each value of the array (from right-to-left) to reduce it to a single value. Opposite of  Array.prototype.reduce().

#### Syntax

```js
const a = ["1", "2", "3", "4", "5"];
const left = a.reduce(function (prev, cur) {
  return prev + cur;
});
const right = a.reduceRight(function (prev, cur) {
  return prev + cur;
});

console.log(left); // "12345"
console.log(right); // "54321"
```

<br>

<a name="arrayReverse"></a>

### Array.prototype.reverse()

---

#### Description

    method reverses an array in place. The first array element becomes the last, and the last array element becomes the first.

#### Syntax

```js
reverse();
```

#### Return value

    It mutates the array and returns the reversed array.

#### Example

```js
const items = [1, 2, 3];
items.reverse();
console.log(items); // [3, 2, 1]
```

<br>

<a name="arrayShift"></a>

### Array.prototype.shift()

---

#### Description

    It is opposite of Array.prototype.pop()

<br>

<a name="arraySlice"></a>

### Array.prototype.slice()

---

#### Description

    returns a shallow copy of a portion of an array into a new array object selected from start to end (end not included) where start and end represent the index of items in that array. The original array will not be modified. A negative index can be used.

#### Syntax

```js
slice(start, end);
```

#### Parameter

    start (optional) = Zero-based index at which to start extraction. If start is undefined, slice starts from the index 0. If start is greater than the index range of the sequence, an empty array is returned.
    end (optional) = The index of the first element to exclude from the returned array. slice extracts up to but not including end. If end is omitted, slice extracts through the end of the sequence (arr.length). If end is greater than the length of the sequence, slice extracts through to the end of the sequence (arr.length).

#### Return value

    A new array containing the extracted elements.

#### Example

```js
let fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
let citrus = fruits.slice(1, 3);

// ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango']
// ['Orange','Lemon']
```

<br>

<a name="arraySome"></a>

### Array.prototype.some()

---

#### Description

    Just like Array.prototype.every() but tests whether at least one element in the array passes the test implemented by the provided function. It returns true if, in the array, it finds an element for which the provided function returns true; otherwise it returns false. It doesn't modify the array.

<br>

<a name="arraySort"></a>

### Array.prototype.sort()

---

#### Description

    sorts the elements of an array in place and returns the sorted array. The default sort order is ascending, built upon converting the elements into strings, then comparing their sequences of UTF-16 code units values.

#### Syntax

```js
sort(compareFn);
```

#### Parameter

    compareFn (optional) = function compareFn(a, b){}
    a = The first element for comparison.
    b = The second element for comparison.

#### Return value

    The sorted array. Note that the array is sorted in place, and no copy is made.

#### Example

```js
const numbers = [4, 2, 5, 1, 3];
numbers.sort(function (a, b) {
  return a - b;
});
console.log(numbers);
// [1, 2, 3, 4, 5]

const numbers = [4, 2, 5, 1, 3];
numbers.sort(function (a, b) {
  return b - a;
});
console.log(numbers);
//  [5, 4, 3, 2, 1]
```

#### Special Note

    a - b > 0	sort a after b
    a - b < 0	sort a before b
    a - b === 0	keep original order of a and b

<br>

<a name="arraySplice"></a>

### Array.prototype.splice()

---

#### Description

    changes the contents of an array by removing or replacing existing elements and/or adding new elements in place. To access part of an array without modifying it, see slice().

#### Syntax

```js
splice(start, deleteCount, item1, item2, itemN);
```

#### Parameter

    start = The index at which to start changing the array. If greater than the length of the array, start will be set to the length of the array. In this case, no element will be deleted but the method will behave as an adding function, adding as many elements as items provided. Accepts negative index.
    deleteCount (optional) = An integer indicating the number of elements in the array to remove from start. If deleteCount is omitted, or if its value is equal to or larger than array.length - start. then all the elements from start to the end of the array will be deleted. However, it must not be omitted if there is any item1 parameter. If deleteCount is 0 or negative, no elements are removed. In this case, you should specify at least one new element.
    itemN (optional) = The elements to add to the array, beginning from start. If you do not specify any elements, splice() will only remove elements from the array.

#### Return value

    An array containing the deleted elements.
    If only one element is removed, an array of one element is returned.
    If no elements are removed, an empty array is returned.

<br>

<a name="arrayToString"></a>

### Array.prototype.toString()

---

#### Description

    It works like Array.prototype.join() without a separator.

<br>

<a name="arrayUnshift"></a>

### Array.prototype.unshift()

---

#### Description

    It is opposite of Array.prototype.push()

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
