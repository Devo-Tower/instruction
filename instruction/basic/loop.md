For Loop
This is the easiest and most common way to look at the elements in an array.
let currentItem;
for (let arrayIndex = 0; arrayIndex < arrayName.length; arrayIndex++) {
  currentItem = arrayName[arrayIndex];
  // Do something with currentItem
}
let currentItem;
This is how we create a variable.  The let keyword finds a piece of memory to store the variable in.  The currentItem is the name we gave the variable, we use this to access what is stored in that piece of memory. 
I like to declare my variables (let/const) outside of the loop.  If you did 
let currentItem = arrayName[arrayIndex];
inside the for loop (which you could do) then you are finding a new piece of memory to store your variable in each time you loop.
for (condition) {body}
In English you’d read this as
for each "condition" do "body"
  OR
while "condition" is true do "body"
Each condition is separated by a ; this is because they are each their own statement, and a ; is how we show where a statement ends.
let arrayIndex = 0;
This is exactly what it looks like, you are creating a counter variable and giving it an initial value.  It is very common to call this variable i (which stands for index), and it almost always starts at 0, but does not have to.
arrayIndex < arrayName.length;
This is how many times the for loop…loops.  In English you would read this as
repeat as long as "arrayIndex" is less than the length of the array
    OR (if arrayIndex starts at 0, see above)
repeat for every index in the array
The reason we use < arrayName.length is because we start counting array indices at 0 . So if we had an array with 10 items in it, the indices for that array would be 
0, 1, 2, 3, 4, 5, 6, 7, 8, 9
so our last index is arrayName.length - 1 so if we tried to do
arrayName[arrayName.length]
we would get an index out of bounds error.
arrayIndex++
This is how our counter variable changes for each loop.  arrayIndex++ is the most common way to write this.  This is a short had way to write
arrayIndex = arrayIndex + 1;
  OR
arrayIndex += 1;
These are all the same way to say that our counter variable gets bigger by 1 for each loop.  
SIDE TRACK:
A couple other ways to you could write a for loop:
 - If you wanted to look at each element starting from the end going forward:
  for (let i = arr.length-1; i >= 0; i--) {}
 - If you wanted to only look at the even index items:
  for (let i = 0; i < arr.length; i += 2) {}
currentItem = arrayName[arrayIndex];
Since you are looping over an array it is safe to assume you want to do something with the array items.  arrayName[arrayIndex] is how you access the element for the current index in your for loop.  You don’t have to save the value like I’m doing here, you could instead do a check on the value like
// This is checking to see if the number at this index is even.
if (arrayName[arrayIndex] % 2 === 0) {  
  // Do something
}
Somewhere in your for loop you should have an arrayName[arrayIndex] *.
* There are exceptions to this, but for now assume this is always true
Why we like for loops
Another way to write a for loop is with a while loop, which I wanted to show you because it’s easier to picture what is happening, but is much more annoying to write
For reference here is our original for loop:
let currentItem;
for (let arrayIndex = 0; arrayIndex < arrayName.length; arrayIndex++) {
  currentItem = arrayName[arrayIndex];
  // Do something with currentItem
};

This is the exact same loop written with a while:
let currentItem;
let arrayIndex = 0; // Our for loop declare statement
while (arrayIndex < arrayName.length) { // Our for loop condition statement
  currentItem = arrayName[arrayIndex];
  // Do something with currentItem
  arrayIndex++; // Our for loop increment statement
}
Other for loops
There are other types of for loops, but this is the easiest to use and the form used the most often so get good at this kind before looking for the others.
