JSON
JSONs are a very common way of transferring information on the web and can be used to pass information to and from a server to the website.
Form
{
  "key1": "key 1 value",
  "key2": "key 2 value",
  ...
  "keyN": "key N value"
}
A JSON object is a list of key/value pairs.
Keys
You can think of a key as a variable name, and its value is the value of that variable.
A key must be a string (surrounded in " ).  It must also be unique to that object. 
{
  "key": "value 1",
  "key": "value 2"
}
is not allowed. A key and its value is separated by a :
Values
A value can be a string, number, boolean, null, array, or another JSON Object . They also do not need to be unique
{
  "stringKey": "string",
  "numberKey": 164,
  "booleanKey": false,
  "nullKey": null,
  "arrayKey": ["element 0", "element 1", "element 2"],
  "jsonKey": {
    "nestedKey1": "value 1",
    "nestedKey2": "value 2",
    "nestedKey3": "value 3"
  },
  "lastKey": "last key value"
}
is perfectly valid.  A value is followed by a , if there is another key/value pair after it.  Some programmers always follow their value with a , even if it is the last pair in the object, so that if they come back later and add another pair they don’t forget the , and break the JSON.
Accessing a value
To look up a value you use it’s key
jsonObject.stringKey === "string"
jsonObject.numberKey === 164
jsonObject.booleanKey === false
jsonObject.nullKey === null
jsonObject.arrayKey === ["element 0", "element 1", "element 2"]
jsonObject.jsonKey === {"nestedKey1": "value 1", "nestedKey2": "value 2", "nestedKey3": "value 3"}
jsonObject.lastKey === "last key value"
Accessing nested arrays/JSONs
To access information inside an array inside a JSON (like in arrayKey) you would do 
jsonObject.arrayKey[0] === "element 0"
jsonObject.arrayKey[1] === "element 1"
jsonObject.arrayKey[2] === "element 2"
This works because jsonObject.arrayKey gives you an array, so putting the [] behind that is the same as doing
let jsonObjectArray = jsonObject.arrayKey; // Stores the array in a variable
jsonObjectArray[0] === "element 0"
For a JSON object in a JSON you would do
jsonObject.jsonKey.nestedKey1 === "value 1"
jsonObject.jsonKey.nestedKey2 === "value 2"
jsonObject.jsonKey.nestedKey3 === "value 3"
This is very similar to the array.  jsonObject.jsonKey gives you a JSON object, so puting another .key behind it is accessing a value inside that nested JSON object
let jsonObjectJson = jsonObject.jsonKey; // Stores the json in a variable
jsonObjectJson.nestedKey1 === "value 1"
Changing a key’s value
jsonObject.key1 = "key 1 new value"

jsonObject.key1 === "key 1 new value"
Other JSON operations
There are a lot of other things you can do with JSONs but the most common are accessing information and changing information so get good at those first.