# Looping

## For Loop

This is the easiest and most common way to look at the elements in an array:

```javascript
let currentItem;
for (let arrayIndex = 0; arrayIndex < arrayName.length; arrayIndex++) {
  currentItem = arrayName[arrayIndex];
  // Do something with currentItem
}
```

This is how we create a variable:

```javascript
let currentItem;
```

The `let` keyword finds a piece of memory to store the variable in.  
The `currentItem` is the name we gave the variable, we use this to access what is stored in that piece of memory. 

I like to declare my variables (`let`/`const`) outside of the loop.
If you did:

```javascript
let currentItem = arrayName[arrayIndex];
```

inside the for loop (which you could do) then you are finding a new piece of memory to store your variable in each time you loop.

```javascript
  for (condition) {
    body
  }
```
In English you’d read this as `for each "condition" do "body"` or `while "condition" is true do "body"`.
Each condition is separated by a `;` this is because they are each their own statement, and a `;` is how we show where a statement ends.

```javascript
let arrayIndex = 0;
```

This is exactly what it looks like, you are creating a counter variable (`arrayIndex`) and giving it an initial value (`0`).  It is very common to call this variable `i` (which stands for index), and it almost always starts at 0, but does not have to.

``` javascript
arrayIndex < arrayName.length;
```

This is how many times the for loop repeats.  In English you would read this as `repeat as long as "arrayIndex" is less than the length of the array`.
The reason we use `< arrayName.length` is because we start counting array indices at 0 . So if we had an array with 10 items in it, the indices for that array would be: `0, 1, 2, 3, 4, 5, 6, 7, 8, 9` so our last index (`9`) is:

```javascript
arrayName.length - 1
```

so if we tried to do:

```javascript
arrayName[arrayName.length] // where arrayName.length === 10
```
we would get an `index out of bounds` error, because the array doesn't contain a 10th index item.

```javascript
arrayIndex++
```

This is how our counter variable changes for each loop.  `arrayIndex++` is the most common way to write this.  This is a short had way to write
`arrayIndex = arrayIndex + 1;` or `arrayIndex += 1;`. These are all the same way to say that our counter variable gets bigger by 1 for each loop.  

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

```javascript
currentItem = arrayName[arrayIndex];
```
Since you are looping over an array it is safe to assume you want to do something with the array items.  `arrayName[arrayIndex]` is how you access the element for the current index in your for loop.  You don’t have to save the value to a variable (`currentItem`) like I’m doing here, you could instead do a check on the value like:
``` javascript
// This is checking to see if the number at this index is even.  % is called a modulo operator.
if (arrayName[arrayIndex] % 2 === 0) {  
  // Do something
}
```
Somewhere in your for loop you should have an `arrayName[arrayIndex]` (there are exceptions to this, but for now assume this is always true).

## While Loop
Another way to write a loop is with a while loop, which I wanted to show you because it’s easier to picture what is happening, but is much more annoying to write.

For reference here is our original for loop:
```javascript
let currentItem;
for (let arrayIndex = 0; arrayIndex < arrayName.length; arrayIndex++) {
  currentItem = arrayName[arrayIndex];
  // Do something with currentItem
};
```

This is the exact same loop written as a while loop:
```javascript
let currentItem;
let arrayIndex = 0; // Our for loop declare statement
while (arrayIndex < arrayName.length) { // Our for loop condition statement
  currentItem = arrayName[arrayIndex];
  // Do something with currentItem
  arrayIndex++; // Our for loop increment statement
}
```

## Other Loops
There are other types of loops, but the basic for loop above is the easiest to use and the form used the most often so get good at this kind before reviewing others:
* [ForEach](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
* [Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
* [Filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
* [Reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)
* [Find](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)
