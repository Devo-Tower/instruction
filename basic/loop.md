# Looping

## For Loop

This is the easiest and most common way to look at the elements in an [array](./array.md):

```javascript
const myArray = [1,2,3];
for (let arrayIndex = 0; arrayIndex < myArray.length; arrayIndex++) {
  const currentItem = myArray[arrayIndex];
  // Do something with currentItem
}
```

> For more information on creating variables (`const`/`let`), see [Variables](./variable.md).

### Basic Structure

```javascript
  for (condition) {
    body
  }
```
In English you’d read this as "for each **condition**, do **body**" or "while **condition** is true, do **body**.

### Condition

Each part of the **condition** is separated by a `;`. This is because each part is actually its own statement, and a `;` is how we show where a statement ends.

> Typically, in Javascript, you'll only see a `;` at the end of a line.  This is because almost all statements in Javascript are written on their own lines.
> There are only a handful of exceptions, and a for loop is one of them.

---

```javascript
let arrayIndex = 0;
```

This is exactly what it looks like: you are initializing a variable (`arrayIndex`) and giving it an initial value (`0`).  It is very common to call this variable `i` (which stands for index), and it almost always starts at 0, but does not have to.

---

``` javascript
arrayIndex < myArray.length;
```

This is how many times the for loop repeats.  In English you would read this as "repeat as long as `arrayIndex` is less than the length of `myArray`.
The reason we use `< myArray.length` rather than `<= myArray.length` is because we start counting array indices at 0, not 1. So if we had an array with 10 items in it, the indices for that array would be: `0, 1, 2, 3, 4, 5, 6, 7, 8, 9` with our last index (`9`).

> Note that you can always access the last element of an array by doing: `myArray[myArray.length - 1]`

> Note that if we instead wrote: `myArray[myArray.length]`, then Javascript would throw an `indexOutOfBounds` error.

---

```javascript
arrayIndex++
```

This is how our variable, `arrayIndex` increments each time **body** is repeated.

> `arrayIndex++` is the most common way to write this.  This is a short had way to write `arrayIndex = arrayIndex + 1;` or `arrayIndex += 1;`. These are all the same way to say that our counter variable gets bigger by 1 for each loop.

#### SIDE TRACK:

A couple other ways to you could write a for loop:

* If you wanted to look at each element starting from the end going forward:

```javascript
for (let i = arr.length-1; i >= 0; i--) {}
```

* If you wanted to only look at the even index items:

```javascript
for (let i = 0; i < arr.length; i += 2) {}
```

### Body

Now that we have the **condition** setup to repeat over every item in an array, it's time we do something with that repeated **body** code.

---

```javascript
currentItem = myArray[arrayIndex];
```
Since you are looping over an array, it is safe to assume you want to do something with the array items.  `myArray[arrayIndex]` is how you access the element for the current index in your for loop. You don’t have to save the value to a variable (`currentItem`) like I’m doing here, you could instead do a check on the value directly like:

``` javascript
if (myArray[arrayIndex] === "hello world") {  
  // Do something
}
```

> Somewhere in your for loop you should have an `myArray[arrayIndex]` (there are exceptions to this, but for now assume this is always true).

## While Loop
Another way to write a loop is with a while loop, which I wanted to show you because it’s easier to picture what is happening, but is much more annoying to write.

For reference here is our original for loop:
```javascript
let currentItem;
for (let arrayIndex = 0; arrayIndex < myArray.length; arrayIndex++) {
  currentItem = myArray[arrayIndex];
  // Do something with currentItem
};
```

This is the exact same loop written as a while loop:
```javascript
let currentItem;
let arrayIndex = 0; // Our for loop declare statement
while (arrayIndex < myArray.length) { // Our for loop condition statement
  currentItem = myArray[arrayIndex];
  // Do something with currentItem
  arrayIndex++; // Our for loop increment statement
}
```

## ForEach Loop

Note that a for loop can loop without needing an array to loop through; for example if you want to sum the numbers 1 through 10:
```javascript
let sum = 0;
for (let i = 1; i <= 10; i++) {
  sum += i;
}
```

However, if you specifically want to loop over an array, you can clean up your for loop by just writing:

```javascript
const myArray = [1,2,3];
myArray.forEach(currentItem => {
  // Do something with currentItem
});
```

## Other Loops
There are other types of loops, but the basic for loop above is the easiest to use and the form used the most often so get good at this kind before reviewing others:
* [Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
* [Filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
* [Reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)
* [Find](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)
