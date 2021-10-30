## Introduction to Modules
---

Every file run by Node has access to the *module* object

Module object looks like this when logged:
```javascript
Module {
  id: '.',
  exports: {},
  parent: null,
  filename: '/Users/superman/codes/moduleCheck.js',
  loaded: false,
  children: [],
  paths: [ ... ] 
}
```
Every file that node runs is considered a separate module

---
### Exporting Modules
---
Notice a inportant aspect of modules: ```exports: {}```

A JS file must *export* the part it wants to be require-able/importable (AKA used by other files). Files usually export an object (remember in JS a function is an object!)

In order to use a function in one file that's declared/defined in another file, we need to export from it's home file + import into file where we want to use it!

If we don't export anything, the default export value will be an empty object (exports: {})

Exporting example:

```javascript 
// myModule.js

const sayHelloTo = function(person) {
  console.log(`Hello, ${person}`);
}
// add this line to the end of the file.
module.exports = sayHelloTo;
```

---
### Requiring a Module
---

Basic Syntax:
```javascript
const sayHelloTo = require('./myModule');
```
Notes:
- Above assumes we have a file named myModule in the same directory as the file requiring the module (otherwise would have to change the path accordingly)
- Don't need a file extension (could do myModule.js, but not necessary). Common convention is to omit the .js extension. 
- Imported object gets assigned to a variable (sayHelloTo)

---
### Summary
---

In Node:
- Code is organized into individual files as **MODULES*
- Every JS file in node is a module
  - We can see its details by calling console.log(module)
- ```module.exports``` tells node what to export from a file
  - Default is ```{}``` (empty object)
- We can import using relative paths (eg. ./myModule)
