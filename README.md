# Complete JavaScript Note

In this note we will discuss all JavaScript methods and properties including Dom, Web Api, Window, Bom & html element object.

## Table Of Contents

1. [Array Methods](#array)

<a name="array"></a>

## Array Methods

<br>

### Array.from()

---

#### Method Description

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

#### Method Description

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

#### Method Description

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

### ()

---

#### Method Description

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
