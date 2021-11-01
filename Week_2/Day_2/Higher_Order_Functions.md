## Higher Order Functions

A higher order function:
- Take in callback functions
- *Operate* on other functions
- Are a MAJOR ASPECT of *functional programming*

## Function Hoisting

- Hoisting is the process by which the interpreter allocates memory to variable and function declarations *before* the code is run
- Variables declared with ```var``` are initialized with default value ```undefined```
- Variables declared with ```let``` or ```const```are NOT initialized as part of hoisting
  - They ARE hoisted, but not initialized with default value ```undefined```. Until they're initialized, any code accessing these variables will throw an exception. 
  - A let/const variable is said to be in the Temporal Dead Zone ('TDZ') from the start of a block until initialization is completed (will throw ReferenceError if called inside TDZ)
- This means that functions can be executed BEFORE they're defined (not good practice, try to avoid this!)

Only declarations are hoisted, not initializations!
eg. 
```javascript 
console.log(num); // Returns 'undefined' from hoisted var declaration (not 6)
var num; // Declaration
num = 6; // Initialization
```

## Function Calling/Invoking vs. Function Passing

- Code inside JS function runs when function is *called/invoked*

### Ways to invoke functions:
1. As a function! (eg. myFunction())
  - Note: this is the same as calling window.myFunction()
2. As a Method! (eg. object1.myFunction())
3. With a Function Constructor
 - eg. (from https://www.w3schools.com/js/js_function_invocation.asp)
 ```javascript 
 // This is a function constructor:
function myFunction(arg1, arg2) {
  this.firstName = arg1;
  this.lastName  = arg2;
}

// This creates a new object
const myObj = new myFunction("John", "Doe");

// This will return "John"
myObj.firstName;
```
4. With ```.call()``` Method
eg. (from https://www.w3schools.com/js/js_function_call.asp)
```javascript
const person = {
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
}
const person1 = {
  firstName:"John",
  lastName: "Doe"
}
const person2 = {
  firstName:"Mary",
  lastName: "Doe"
}

// This will return "John Doe":
person.fullName.call(person1);
```
5. With ```.apply()``` Method
  - To write a method that can be used on different objects
  - Similar to call() method but takes an array instead of separate parameters

### Function Passing
## Passing by Reference or By Value
notes from https://dmitripavlutin.com/value-vs-reference-javascript/
### Passing by Value
- Passing by value happens when assigning **primitives**
- Every time you assign a value to a variable, a copy of that value is created
- Two variables holding values will be equal if the values are equal, regardless of where those values originate from

### Passing by Reference
- Passing by reference happens when assigning **objects**
- If you modify an object, then all variables that reference that object will see a change
- Two different objects may contain the same values, but they cannot be directly compared using === because they are pointing to two *different* references. In other words, two variables holding references will only be equal if they're referencing *exactly* the same object

