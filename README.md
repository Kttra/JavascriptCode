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
```js
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
```
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
**Arrow Functions**
-----------------------

```js
//Anonymous function
var ourResults = function(){
	return new Date();
};
//Arrow function version
var magic = () => {
	return new Date();
};
//Even shorter version
var magic = () => new Date();

//arr1, arr2 are the paremeters we passed
var myConcat = (arr1, arr2) => {
	return arr1.concat(arr2);
};
//Shorter version
const myConcat = (arr1, arr2) => arr1.concat(arr2);
console.log(myConcat([1,2],[3,4,5])); //[1,2,3,4,5]
```

**Rest Operator**
---------------------
Allows you to create a function that takes a different amount of arguments.
```js
const sum = (function(){
	return function sum(...args){
		//const args = [x,y,z];
		return args.reduce((a,b)=>a+b,0);
	};
})();
console.log(sum(1,2,3)); //6
```

**Destructuring**
-------------
```js
var voxel = {x: 3.6, y: 7.4, z: 6.54};

var x = voxel.x; //x = 3.6
var y = voxel.y; //y = 7.4
var z = voxel.z; //z = 6.54

const{x: a, y: b, z: c} = voxel; //a=3.6, b=7.4,c=6.54 //quicker way of assigning things from an object into variables

const [z, x, , y] = [1, 2, 3, 4, 5, 6, 7, 8, 9];
console.log(z, x, y); //1, 2, 4
let a = 8, b = 6;
(() => {
	"use strict";
	[a, b] = [b, a];
})();
console.log(a, b); //6, 8

const source = [1,2,3,4,5,6,7,8,9,10];
function removeFirstTwo(list){
	const [a, b, ...arr] = list;
	return arr;
}
const arr = removeFirstTwo(source);
console.log(arr); //[1,2,3,4,5,6,7,8,9,10]
console.log(source); //[3,4,5,6,7,8,9,10]
```
**Template Literals**
-------------------
Type of string that makes creating complex strings easier. Denoted by a backtick, ``` ` ```.
```js
const person = {
	name: "Zodiac",
	age: 56
};

const greeting = `Hello, my name is ${person.name}! I am ${person.age} years old.`;
console.log(greeting);
```
**Object Function**
---------------
```js
const bicycle = {
	gear: 2,
	setGear(newGear){
		“use strict”;
		this.gear = newGear;
	}
};
```

**Class Syntax**
--------------------
```js
var SpaceShuttle = function(targetPlanet){
	this.targetPlanet = targetPlanet;
}
//Older way to create class
var zeus = new SpaceShuttle(‘Jupiter’);
console.log(zeus.targetPlanet);

class SpaceShuttle{
	constructor(targetPlanet){
		this.targetPlanet = targetPlanet;
	}
}
var zeus = new SpaceShuttle(‘Jupiter’)
console.log(zeus.targetPlanet);

//Creating a vegetable class
function makeClass(){
	class Vegetable{
	 	constructor(name){
			this.name = name;
		}
	}
	return Vegetable;
}
const Vegetable = makeClass();
const carrot = new Vegetable(‘carrot’);
console.log(carrot.name);
```

**Private Variables in Class**
-------------------
```js
class Book{
	constructor(author){
		this._author = author;
	}
	//getter
	get writer(){
		return this._author; 
	}
	//setter
	set writer(updatedAuthor){
		this._author = updatedAuthor;
	}
}
function makeClass(){
	class Thermostat{
		constructor(temp){
			this._temp = 5/9*(temp-32);//Convert to C
		}
		get temperature(){
			return this._temp; //_ signifies it's a private variable
		}
		set temperature(updatedTemp){
			this._temp = updatedTemp;
		}
	}
	return Thermostat;
}
const Thermostat = makeClass();
const thermos = new Thermostat(76);
let temp = thermos.temperature; //Property
thermos.temperature = 26;
temp = thermos.temperature;
```

**Import & Export**
----------
```js
export const capitalizeString = str => str.toUpperCase();

import { capitalizeString } from "./string_function.js";
const cap = capitalizeString(“Hello!”);

//Import everything
import * as capitalizeString from “./string_funciton”;
```
