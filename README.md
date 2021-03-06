# documentation for [sci](https://github.com/AndroidLollipop/sci), a programming language created for fun
https://github.com/AndroidLollipop/sci
## features
### functions and closures
functions are first-class citizens in sci. this means that you can pass functions as parameters to other functions and return functions from functions.  
  
example:    
var e = require("./simpleAndCleanInterfaceForRepl.js")  
var repl = e.getRepl()  
console.log(repl("num closure(){num add(){skye = skye + 1; return skye}; num skye = 1; return add}"))  
console.log(repl("num clo = closure()"))  
console.log(repl("clo()"))  
console.log(repl("clo()"))  
console.log(repl("clo()"))  
  
output:  
{ type: 'number', value: 2 }  
{ type: 'number', value: 3 }  
{ type: 'number', value: 4 }  
  
clo accesses the variable skye which is in the scope of its parent, which is no longer accessible as it has returned. this is called a closure.  
  
in sci, each function can access the scope it is created in and the parameters it is passed, no more, no less.  
setting undeclared variables makes them global.  
  
example:  
var e = require("./simpleAndCleanInterfaceForRepl.js")  
var repl = e.getRepl()  
console.log(repl("num slowFibonacci(n){if(n < 3){return 1};return slowFibonacci(n-1)+slowFibonacci(n-2)}"))  
console.log(repl("slowFibonacci(10)"))  
  
output:  
{ type: 'number', value: 55 }  
this is a classic but very slow recursive function.
### standard features
sci supports many of the features you'd expect from any programming language, like arrays, loops, and conditionals. for function calls, array literals, and array lookups, everything is evaluated from left to right (this matters since evaluating functions can cause side effects). for array assignments, however, the assigned value is evaluated before the array index.
