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
    var moo = "Mooo"
    let baz = "Bazz";
    console.log(moo, baz); // Mooo Bazz
  }

  console.log(moo); // Mooo
  console.log(baz); // ReferenceError
}
run();
```
