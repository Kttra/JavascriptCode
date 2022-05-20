# JavascriptCode
Javascript code reference. A compilation of code that is used in Javascript.

**Comments**
-------------------
```js
//in-line comment
/* Block comment */
```

**Write to console**
-------------------
```js
Console.Log("Hello World")
```

**Data Types & Variables**
----------------
Data types: undefined, null, Boolean, string, symbol, number, object
Variables declared by var keyword are scoped to the immediate function body while let variables are scoped to the immediate enclosing block denoted by ```
{ } ```
```js
var myName = “Tim”;
myName = 8;
let ourName = “Name”;
const pi = 3.14;
```

**Var vs Let**
-----------------
```js
function run() {
  var foo = "Foo";
  console.log(foo); // Foo

  {
    var moo = "Mooo";
    let baz = "Bazz";
    console.log(moo, baz); // Mooo Bazz
  }

  console.log(moo); // Mooo
  console.log(baz); // ReferenceError
}
run();
```

**Strings**
-----------------
```js
firstName = “Tim”;
var myStr = “I am a \“double quoted\” string inside \“double quotes\””;
myStr = '<a href="http://example.com" target="_blank">Link</a>';
firstName.length; //5
firstName[0]; //T
firstName[0] = “A”; //Cannot do b/c strings are immuatable
firstName = “Jim”; //This is allowed though
```

**Escape Sequences in Strings**
----------------------
```js
\’ 	//single quote
\”	//double quote
\\	//backslash
\n	//newline
\r	//carriage return
\t	//tab
\b	//backspace
\f	//form feed
```

**Concatenation**
----------------------
```js
var outstr = “I come first ” + “I come second”;
```

**Functions**
-----------------
```js
function wordBlanks(myNoun, myAdjective, myVerb, myAdverb){
	var result = “”;
	result += "The " + myAdjective + " " + myNoun + " " + myVerb + " to the store " + myAdverb + "."}
}
console.log(worldBlanks(“dog”, “big”, “ran”, “quickly”)); //The big dog ran to the store quickly.
function addFive(num){
	return num + 5;
}
```

**Arrays**
-----------------
```js
var ourArray = [“Kevin”, 23];
//Nested array
var myArray = [[“The universe”, 42], [“everything”, 2]];
var array2 = [1, 2, 3];
array2[0]; //1
array2[0] = 30; //[30, 2, 3]
//Array of arrays
myArray = [[1,2,3],
           [4,5,6],
           [7,8,9],
           [[10, 11, 12],13, 14]]];
var myData = myArray[0,0]; //1
//push//pop
var ourArray = [“K”, “J”, “cat”];
ourArray.push([“happy”, “joy”]);
var removedElement = ourArray.pop(); //Removes last element
ourArray.shift(); //Removes first element
overArray.unshift(“Happy”); //Adds to beginning of the array
```
**Printing out an Array**
---------------------
Return an array after appending an element and shifting it.

```js
function nextInLine(arr, item){
	arr.push(item); //Push in 6
	return arr.shift(); //Return first item after shifting
}
var testArr = [1,2,3,4,5];

console.log("Before: " + JSON.stringify(testArr)); //Before: [1,2,3,4,5]
console.log(nextInLine(testArr, 6)); //1
console.log("After: " + JSON.stringify(testArr)); //After: [2,3,4,5,6]
```

**If Statements**
--------------
```js
//If statement example
let isTrue = true;
if(isTrue){
	console.log("Yes, it's true.");
}
else{
    console.log("Not true.");
}
//Equality operator
let val = 10;
if(val == 12){
    //Do something
}
//Strict equality operator
if(3 === 3){
    //True
}
else if(3 === '3'){
    //False
}
if(3 == 3){
    //True
}
if(3 == '3'){
    //True
}
```

