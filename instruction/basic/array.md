# Array
If you think of a `variable` as a box (with the name/label written on the outside, and the value stored inside [which can be taken out and replaced by something else]) then an `array` is a list of boxes.  The only difference is we don’t pick the names of our boxes, the names are given to them based on their location in the list, so the first box is name `0` and the next box is `1` and so on.
## Form
```
[ 0, 1, 2, ... , length-1 ]
```
## Create
* Empty
```
let arrayName = [];
```
* With initial values
```
let arrayName = ["value 1", "value 2", "value 3", ... , "value n"];
```
## Length of array
```
arrayName.length
```
## Access
```
let item = arrayName[indexOfItem];
```
The array index starts at `0` and goes to `arrayName.length-1`
## Add
* To the end
```
arrayName.push("valueToAdd");
```
* To the front
```
arrayName.unshift("valueToAdd");
```
## Remove
* From the end
```
arrayName.pop();
```
* From the front
```
arrayName.shift();
```
Note that you don’t have to say what you are removing, just what end you want to remove from.  If you want to do something with the element you remove you need to save it in a variable, otherwise it’s just gone.
```
let saveRemovedItem = arrayName.pop();
   OR
let saveRemovedItem = arrayName.shift();
```
## Items (elements) in an array
The correct term for an array item is `element`.  You can store anything in an array, but for now I’ll just list a few common ones
```
 - strings
 - numbers
 - JSON Objects
 - arrays
 ```
*strings*
```
["string at index 0", "string at index 1", "string at index 2"]
```
*numbers*
```
[0, 1, 2]
```
*JSON Objects*
```
[{"key": "object 0 value"}, {"key": "object 1 value"}, {"key": "object 2 value"}]
```
Even though a JSON object is more complicated than a string or number, accessing them in the array is exactly the same
```
jsonArray[0] === {"key": "object 0 value"}
jsonArray[1] === {"key": "object 1 value"}
jsonArray[2] === {"key": "object 2 value"}
```
*arrays*
```
[["subarray 0 item 0", "subarray 0 item 1", "subarray 0 item 2"], ["subarray 1 item 0", "subarray 1 item 1", "subarray 1 item 2"], ["subarray 2 item 0", "subarray 2 item 1", "subaray 2 item 2"]]
```
Like the JSON objects array this feels more complicated but accessing elements is still the same
```
arrayArray*[0] === ["subarray 0 item 0", "subarray 0 item 1", "subarray 0 item 2"]
arrayArray[1] === ["subarray 1 item 0", "subarray 1 item 1", "subarray 1 item 2"]
arrayArray[2] === ["subarray 2 item 0", "subarray 2 item 1", "subarray 2 item 2"]
```
*usually you’d call this a 2dArray but I wanted to be consistent
An array of arrays is great for keeping track of a grid, like if you were making a chess game.
## Accessing JSON/Array info inside an array
*JSON*
Using the array examples above if you wanted to access something inside a JSON inside an array you would do
```
jsonArray[0].key === "object 0 value"
jsonArray[1].key === "object 1 value"
jsonArray[2].key === "object 2 value"
```
And this is the same thing as line 1 written out long so you can understand what is happening
```
let jsonObjectInArray = jsonArray[0];
let getValueFromJsonObjectInArray = jsonObjectInArray.key;

getValueFromJsonObjectInArray === "object 0 value"
```
*Array*
Now the same thing for the array inside the array
```
arrayArray[0][0] === "subarray 0 item 0"
arrayArray[0][1] === "subarray 0 item 1"
arrayArray[0][2] === "subarray 0 item 2"
arrayArray[1][0] === "subarray 1 item 0
arrayArray[1][1] === "subarray 1 item 1"
arrayArray[1][2] === "subarray 1 item 2"
arrayArray[2][0] === "subarray 2 item 0
arrayArray[2][1] === "subarray 2 item 1"
arrayArray[2][2] === "subarray 2 item 2"
```
And this is line 1 written out long
```
let subarrayZero = arrayArray[0];
let elementZeroInSubarrayZero = subarrayZero[0];

elementZeroInSubarrayZero === "subarray 0 item 0"
```
## Other methods:
There are other things arrays can do, I just listed the most common.  To see all the other methods (when you feel confident with these and are ready for more) you can look at: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array
