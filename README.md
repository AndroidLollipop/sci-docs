# documentation for [sci](https://github.com/AndroidLollipop/sci), a programming language created for fun
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
  
clo accesses the variable skye which is in the scope of its parent, which is no longer accessible as it has returned. this is called a closures.