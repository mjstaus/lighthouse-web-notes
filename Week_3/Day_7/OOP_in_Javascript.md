## Object Oriented Programming in JavaScript

In OOP, we want to group related pieces of code together into an **object**

eg. All these dog variables, arrays, function, etc. can be grouped into an object
```javascript
const dog = {
  name: "Ellie"
  sound: "ggrrrruff",
  favoriteThings: ["chewies", "Martha", "napping"],
  dislikes: ["rain", "baths", "mail carriers"]
  dogBreed: "chi-spaniel",
  speak: function() {
    console.log(`${this.dogBreed} says ${this.dogSound}`);
  }
};
```
---
### Object Terminology
---
- **State** = Information contained within an object (properties/key-value pairs)
- **Method** = function stored in an object
- **Behaviour** = Stuff an object can *do* (via methods)

All of this means that state + logic can be bundled up together in an object and PASSED AROUND!

---
### `this`
---

Value of `this` is determined at the time of the call and depends on CONTEXT

Inside a method, `this` refers to the object the method was called on

> Use `this` whenevever your method is calling a property/method on the SAME OBJECT

