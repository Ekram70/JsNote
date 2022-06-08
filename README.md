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
1. [String Methods](#string)
   1. [String.fromCharCode()](#stringFromCharCode)
   1. [String.prototype.at()](#stringAt)
   1. [String.prototype.charAt()](#stringCharAt)
   1. [String.prototype.charCodeAt()](#stringCharCodeAt)
   1. [String.prototype.concat()](#stringConcat)
   1. [String.prototype.endsWith()](#stringEndsWith)
   1. [String.prototype.includes()](#stringIncludes)
   1. [String.prototype.indexOf()](#stringIndexOf)
   1. [String.prototype.lastIndexOf()](#stringLastIndexOf)
   1. [String.prototype.match()](#stringMatch)
   1. [String.prototype.matchAll()](#stringMatchAll)
   1. [String.prototype.padEnd()](#stringPadEnd)
   1. [String.prototype.padStart()](#stringPadStart)
   1. [String.prototype.repeat()](#stringRepeat)
   1. [String.prototype.replace()](#stringReplace)
   1. [String.prototype.replaceAll()](#stringReplaceAll)
   1. [String.prototype.search()](#stringSearch)
   1. [String.prototype.slice()](#stringSlice)
   1. [String.prototype.split()](#stringSplit)
   1. [String.prototype.startsWith()](#stringStartsWith)
   1. [String.prototype.substring()](#stringSubstring)
   1. [String.prototype.toLowerCase()](#stringToLowerCase)
   1. [String.prototype.toString()](#stringToString)
   1. [String.prototype.toUpperCase()](#stringToUpperCase)
   1. [String.prototype.trim()](#stringTrim)
   1. [String.prototype.trimEnd() /String.prototype.trimRight()](#stringTrimEnd)
   1. [String.prototype.trimStart() /String.prototype.trimLeft()](#stringTrimStart)
   1. [String.prototype.valueOf()](#stringValueOf)

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

<a name="string"></a>

## String Method Methods

<a name="stringFromCharCode"></a>

### String.fromCharCode()

---

#### Description

    returns a string created from the specified sequence of UTF-16 code units.

#### Syntax

```js
String.fromCharCode(num1, num2, ..., numN)
```

#### Parameter

    num1...numN = A sequence of numbers that are UTF-16 code units

#### Return value

    A string of length N consisting of the N specified UTF-16 code units.

#### Example

```js
String.fromCharCode(65, 66, 67); // returns "ABC"
```

<br>

<a name="stringAt"></a>

### String.prototype.at() - Experimental

---

#### Description

    Works like Array.prototype.at()

<br>

<a name="stringCharAt"></a>

### String.prototype.charAt()

---

#### Description

    it works like String.prototype.at() but doesn't accept negative index. If the index is not between string length it returns empty string.

<br>

<a name="stringCharCodeAt"></a>

### String.prototype.charCodeAt()

---

#### Description

    It works like String.prototype.charAt() but return the ascii value of the given index. It return NaN if is out of range of out of index.

<br>

<a name="stringConcat"></a>

### String.prototype.concat()

---

#### Description

    It is similar to Array.prototype.concat()

#### Special Note

    It is strongly recommended to use assignment operators (+=) instead of String.prototype.concat()

<br>

<a name="stringEndsWith"></a>

### String.prototype.endsWith()

---

#### Description

    determines whether a string ends with the characters of a specified string, returning true or false as appropriate.

#### Syntax

```js
endsWith(searchString, length);
```

#### Parameter

    searchString = The characters to be searched for at the end of str.
    length (optional) = If provided, it is used as the length of str. Defaults to str.length.

#### Return value

    true if the given characters are found at the end of the string; otherwise, false.

#### Example

```js
let str = "To be, or not to be, that is the question.";
console.log(str.endsWith("question.")); // true
console.log(str.endsWith("to be")); // false
console.log(str.endsWith("to be", 19)); // true
```

<br>

<a name="stringIncludes"></a>

### String.prototype.includes()

---

#### Description

    performs a case-sensitive search to determine whether one string may be found within another string, returning true or false as appropriate.

#### Syntax

```js
includes(searchString, position);
```

#### Parameter

    searchString = A string to be searched for within str.
    position (optional) = The position within the string at which to begin searching for searchString. (Defaults to 0.)

#### Return value

    true if the search string is found anywhere within the given string; otherwise, false if not.

#### Example

```js
"Ekram".includes("a");
// true
"Ekram".includes("E", 3);
// false
```

<br>

<a name="stringIndexOf"></a>

### String.prototype.indexOf()

---

#### Description

    It works similar to Array.prototype.indexOf()

#### Syntax

```js
indexOf(searchString, position);
```

#### Example

```js
"hello".indexOf(); //-1
"hello".indexOf("o", 10); //-1
"hello".indexOf("o", -5); //4
```

<br>

<a name="stringLastIndexOf"></a>

### String.prototype.lastIndexOf()

---

#### Description

    It is opposite of String.prototype.indexOf()

#### Example

```js
"hello".lastIndexOf(); //-1
"hello".lastIndexOf("o", 10); //4
"hello".lastIndexOf("o", -5); //-1
```

<br>

<a name="stringMatch"></a>

### String.prototype.match()

---

#### Description

    retrieves the result of matching a string against a regular expression.

#### Syntax

```js
match(regexp);
```

#### Parameter

    regexp = A regular expression object.

    If regexp is a non-RegExp object, it is implicitly converted to a RegExp by using new RegExp(regexp).

    If you don't give any parameter and use the match() method directly, you will get an Array with an empty string: [""].

#### Return value

    An Array whose contents depend on the presence or absence of the global (g) flag, or null if no matches are found.

#### Example

```js
const paragraph = "The quick brown. It barked.";
const regex = /[A-Z]/g;
const found = paragraph.match(regex);
console.log(found);
// ["T", "I"]
```

<br>

<a name="stringMatchAll"></a>

### String.prototype.matchAll()

---

#### Description

    The matchAll() method returns an iterator of all results matching a string against a regular expression, including capturing groups.

#### Return value

    An iterator (which is not a restartable iterable) of matches.

<br>

<a name="stringPadEnd"></a>

### String.prototype.padEnd()

---

#### Description

    pads the current string with a given string (repeated, if needed) so that the resulting string reaches a given length. The padding is applied from the end of the current string.

#### Syntax

```js
padEnd(targetLength, padString);
```

#### Parameter

    targetLength = The length of the resulting string once the current str has been padded. If the value is lower than str.length, the current string will be returned as-is.

    padString (optional) = The string to pad the current str with. Default is space.

#### Return value

    A String of the specified targetLength with the padString applied at the end of the current str.

#### Example

```js
"abc".padEnd(10); // "abc       "
"abc".padEnd(10, "foo"); // "abcfoofoof"
"abc".padEnd(6, "123456"); // "abc123"
"abc".padEnd(1); // "abc"
```

<br>

<a name="stringPadStart"></a>

### String.prototype.padStart()

---

#### Description

    It works same as String.prototype.padEnd() but it starts padding from starting of the string.

<br>

<a name="stringRepeat"></a>

### String.prototype.repeat()

---

#### Description

     constructs and returns a new string which contains the specified number of copies of the string on which it was called, concatenated together.

#### Syntax

```js
repeat(count);
```

#### Parameter

    count = An integer between 0 and +Infinity, indicating the number of times to repeat the string.

#### Return value

    A new string containing the specified number of copies of the given string.

#### Example

```js
"abc".repeat(-1); // RangeError
"abc".repeat(0); // ''
"abc".repeat(1); // 'abc'
"abc".repeat(2); // 'abcabc'
"abc".repeat(3.5); // 'abcabcabc' (count will be converted to integer)
"abc".repeat(1 / 0); // RangeError
```

#### Special Note

    RangeError: repeat count must be non-negative.
    RangeError: repeat count must be less than infinity and not overflow maximum string size.

<br>

<a name="stringReplace"></a>

### String.prototype.replace()

---

#### Description

    returns a new string with some or all matches of a pattern replaced by a replacement. The pattern can be a string or a RegExp, and the replacement can be a string or a function called for each match. If pattern is a string, only the first occurrence will be replaced.

#### Syntax

```js
replace(regexp | substr, newSubstr | replacerFunction);
```

#### Parameter

    regexp = A RegExp object or literal. The match or matches are replaced with newSubstr or the value returned by the specified replacerFunction.

    substr = A string that is to be replaced by newSubstr. It is treated as a literal string and is not interpreted as a regular expression. Only the first occurrence will be replaced.

    newSubstr = The string that replaces the substring specified by the specified regexp or substr parameter. If newSubstr is an empty string, then the substring given by substr, or the matches for regexp, are removed (rather then being replaced).

    replacerFunction = A function to be invoked to create the new substring to be used to replace the matches to the given regexp or substr.

#### Return value

    A new string, with some or all matches of a pattern replaced by a replacement.

#### Example

```js
const p = "dog dog cat rat";
console.log(p.replace("dog", "cow"));
// "cow dog cat rat"
```

<br>

<a name="stringReplaceAll"></a>

### String.prototype.replaceAll()

---

#### Description

    it is similar to String.prototype.replace() with a global flag.

#### Special Note

    When using a `regexp` you have to set the global ("g") flag; otherwise, it will throw a TypeError: "replaceAll must be called with a global RegExp".

<br>

<a name="stringSearch"></a>

### String.prototype.search()

---

#### Description

    executes a search for a match between a regular expression and this String object.

#### Syntax

```js
search(regexp);
```

#### Parameter

    regexp = A regular expression object.

    If a non-RegExp object regexp is passed, it is implicitly converted to a RegExp with new RegExp(regexp).

#### Return value

    The index of the first match between the regular expression and the given string, or -1 if no match was found.

#### Example

```js
let str = "hey JudE";
let re = /[A-Z]/g;
let reDot = /[.]/g;
console.log(str.search(re));
// returns 4, which is the index of the first capital letter "J"
console.log(str.search(reDot));
// returns -1 cannot find '.' dot punctuation
```

<br>

<a name="stringSlice"></a>

### String.prototype.slice()

---

#### Description

    extracts a section of a string and returns it as a new string, without modifying the original string.

#### Syntax

```js
slice(beginIndex, endIndex);
```

#### Parameter

    beginIndex = index at which to begin extraction.
    endIndex (optional) = The index of the first character to exclude from the returned substring.

#### Return value

    A new string containing the extracted section of the string.

#### Example

```js
const str = "The quick brown fox jumps over the lazy dog.";
console.log(str.slice(31));
// "the lazy dog."
console.log(str.slice(4, 19));
// "quick brown fox"
console.log(str.slice(-4));
// "dog."
console.log(str.slice(-9, -5));
// "lazy"
```

#### Special Note

    If beginIndex is omitted, undefined, or cannot be converted to a number it begins extraction from the beginning of the string.

    endIndex has excluding behaviour.

<br>

<a name="stringSplit"></a>

### String.prototype.split()

---

#### Description

    divides a String into an ordered list of substrings, puts these substrings into an array, and returns the array.

#### Syntax

```js
split(separator, limit);
```

#### Parameter

    separator (optional) = The pattern describing where each split should occur. The separator can be a simple string or it can be a regular expression.

    limit (optional) = A non-negative integer specifying a limit on the number of substrings to be included in the array. If limit is 0, [] is returned.

#### Return value

    An Array of strings, split at each point where the separator occurs in the given string.

#### Example

```js
"test".split(); // ["test"]
"best".split("t"); // ["tes", ""]
"best".split("b"); // ["", est]
"test.test.test".split(".", 1); // ["test"]
"test.test.test".split(".", 0); // []
"test.test.test".split(".", 50); // ["test","test","test"]
"test.test.test".split(".", -5); // ["test","test","test"]
"test.test.test".split([".", ","]); // ["test","test","test"]
```

#### Special Note

    If the separator is an array, then that Array is coerced to a String and used as a separator.

<br>

<a name="stringStartsWith"></a>

### String.prototype.startsWith()

---

#### Description

    It is opposite of String.prototype.endsWith(). it starts from the beginning of the string.

<br>

<a name="stringSubstring"></a>

### String.prototype.substring()

---

#### Description

    returns the part of the string between the start and end indexes, or to the end of the string.

#### Syntax

```js
substring(indexStart, indexEnd);
```

#### Parameter

    indexStart = The index of the first character to include in the returned substring.
    indexEnd (optional)  = The index of the first character to exclude from the returned substring.

#### Return value

    A new string containing the specified part of the given string.

#### Example

```js
const str = "Mozilla";
console.log(str.substring(1, 3));
// "oz"
console.log(str.substring(2));
// "zilla"
```

#### Special Note

    Negative index or any vale that cannot be converted to a number is treated as 0

    If indexEnd is omitted, substring() extracts characters to the end of the string.

    If indexStart is equal to indexEnd, substring() returns an empty string.

    If indexStart is greater than indexEnd, then the effect of substring() is as if the two arguments were swapped;

<br>

<a name="stringToLowerCase"></a>

### String.prototype.toLowerCase()

---

#### Description

    returns the calling string value converted to lower case.

#### Syntax

```js
toLowerCase();
```

#### Return value

    A new string representing the calling string converted to lower case.

#### Example

```js
console.log("ALPHABET".toLowerCase()); // 'alphabet'
```

<br>

<a name="stringToString"></a>

### String.prototype.toString()

---

#### Description

    it converts a string object that is constructed with new keyword to a normal string.

<br>

<a name="stringToUpperCase"></a>

### String.prototype.toUpperCase()

---

#### Description

    It is opposite of String.prototype.toLowerCase()

<br>

<a name="stringTrim"></a>

### String.prototype.trim()

---

#### Description

    removes whitespace from both ends of a string and returns a new string

#### Syntax

```js
trim();
```

#### Return value

    A new string representing str stripped of whitespace from both its beginning and end.

#### Example

```js
const greeting = "   Hello world!   ";
console.log(greeting.trim());
// "Hello world!";
```

<br>

<a name="stringTrimEnd"></a>

### String.prototype.trimEnd() /String.prototype.trimRight()

---

#### Description

    It works like String.prototype.trim() but only removes whitespace from right side.

<br>

<a name="stringTrimStart"></a>

### String.prototype.trimStart() /String.prototype.trimLeft()

---

#### Description

    It works like String.prototype.trim() but only removes whitespace from left side.

<br>

<a name="stringValueOf"></a>

### String.prototype.valueOf()

---

#### Description

    It works like String.prototype.toString()

<br>

<a name=""></a>

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
