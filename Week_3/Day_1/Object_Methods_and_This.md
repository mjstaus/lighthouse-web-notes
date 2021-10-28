## Object Methods and 'This'

---

### Functions as Object Properties (AKA METHODS!)
---

We can store a function on an object as a property! This is called an object "method"

Example:
```javascript
const person = {
  firstName: 'Martha',
  lastName:  'Staus',
  fullName: function() {
    return this.firstName + ' ' + this.lastName;
  }
}

// Nice, now I could say:
console.log('Hello, ' + person.fullName());
//returns "Hello, Martha Staus"

```
- In this example, the function exists *inside* the person object. 
- Functions attached to objects in this way are called methods. 
- Other code can now call this function/method from outside the object
- Notice the use of "this" keyword in the method. 
  - It allows the method to refer to the object that it's within. 
  - Object methods are the most common use case for "this"

---
  ### Introduction to "This"
---
> IMPORTANT DISCLAIMER: This introduction is simplistic and technically inaccurate. It is neither important nor reasonable for you to truly understand "this" at the moment. It's okay for now, just be cool. 


- When used within an object's method, "this" points to the object where it resides. 
- **"this" refers to the object the method/function was called on. 

