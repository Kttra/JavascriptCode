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
var ourArray = ["K", 23];
//Nested array
var myArray = [["The universe", 42], ["everything", 2]];
var array2 = [1, 2, 3];
array2[0]; //1
array2[0] = 30; //[30, 2, 3]
array2.length; //3
//Array of arrays
myArray = [[1,2,3],
           [4,5,6],
           [7,8,9],
           [[10, 11, 12],13, 14]];
var myData = myArray[0,0]; //1
//push//pop
var ourArray = ["K", "J", "cat"];
ourArray.push(["happy", "joy"]);
var removedElement = ourArray.pop(); //Removes last element
ourArray.shift(); //Removes first element
ourArray.unshift("Happy"); //Adds to beginning of the array
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
```
**Equality operators**
--------------
```js
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

**While Loop and Do While Loop**
------------------------------
```js
var i = 0;
while(i < 4){
    i++;
}
do{
    i++
}while(i<5);
```
**For Loop and For Each**
-------------------------
```js
//Normal for loop
for(var i = 0; i < 4; i++){
    //Do stuff 
}
//Foreach
const fruits = ["apple", "orange", "cherry"];
fruits.forEach(element => {
    console.log(element);
});
```
**Switch Statement**
-----------------------
```js
val = 1;

switch(val){
	case 1:
	case 10:
		answer = “alpha”
		break;
	case 2:
		answer = “beta”;
		break;
	default:
		answer = “N/A”
		break;
}
```
**Objects**
---------------
```js
var ourDog = {
	"name": "Camper",
    "legs": 4,
    "tails": 1,
    "friends": ["everything!"],
};
var testObj = {
	"hat": "ballcap",
	"shirt": "jersey",
	"shoes": "cleats",
};
var hatValue = testObj.hat;
var shirtValue = testObj.shirt;
var shoesValue = testObj[“shoes”]; //Another way to access property

var myDog = {
"name": "Camper",
    "legs": 4,
    "tails": 1,
    "friends": [],
}
myDog.name = "Happy";
//Adding new properties
myDog['bark'] = "woof!"
//Delete properties
delete myDog.bark;

//Check property
var myObj = {
	gift: "pony",
	pet: "kitten",
	bed: "sleigh"
};
var hasProp = myObj.hasOwnProperty("gift"); //becomes true
```
**Random**
------------------
```js
var randomNumBet0and19 = Math.floor(Math.random()*20); //0-19

//Random number between myMin & myMax, inclusive
function ourRandomRange(myMin, myMax){
    return Math.floor(Math.random() * (myMax - myMin + 1)) + myMin;
}
console.log(ourRandomRange(1, 9)); //1-9
```
**Conversion**
----------------
```js
parseInt(“42”); //Returns 42

//binary number conversion
function binToInteger(str){
	return praseInt(str, 2);
}
binToInteger(“10011”);
```

**Ternary Operator**
-----------------
//condition ? statement-if-true : statement-if-false;
function checkEqual(a, b){
	return a===b ? true:false;
	//return a===b; //same result
}
checkEqual(1,2);

function checkSign(num){
	return num > 0 ? "positive": num < 0 ? "negative" : "zero"; 
}
console.log(checkSign(0));

**Difference between Let & Var, Const**
-----------------------------
Starting with ES6 you can use let and const.
let only allows you to declare once. Scope of let is limited to block statement or expression it is declared in.

```js
function checkScope(){
	"use strict"; //Catch common coding mistakes and unsafe actions
	var i = "function scope";
	if(true){
		i = "block scope"; 
		console.log(i); //block scope
	} 
	console.log(i); //block scope
return i;
}
function checkScope2(){
	"use strict";
	let i = "function scope";
	if(true){
		let i = "block scope"; 
		console.log(i); //block scope
	} 
	console.log(i); //function scope
return i;
}
//block scope function scope

//Const cannot be reassigned, arrays can be reassigned by index
const WORD = "Cool";
```
