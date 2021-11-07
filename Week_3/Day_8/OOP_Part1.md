## OOP Part 1: Classes and Instances
---
### Classes are Blueprints
---
Blueprints contain all the instructions for building a new house, but a blueprint is not a house. We can use the blueprint to build as many houses as we want, and each house is unique while all being built based on the same blueprint

**Classes** are blueprints (templates) that we use to create **instances** of objects!

---
### Classes
---
Declare a class like so:
```javascript
class Dog {
}
```

Important points: 
- Class name should be a noun
- Capitalize class name

Create a new object from a class like so:
```javascript
let Ellie = new Dog();
let Pippi = new Dog();
```

Ellie and Pippi are both *instances* of the Dog class. 

---
### Methods and Properties
---
Let's say for class Pizza, we want each pizza to start with a cheese topping and then we can add other toppings to our pizzas:

```javascript
class Pizza {

  constructor() {
    this.toppings = ["cheese"];
  }

  addTopping(topping) {
    this.toppings.push(topping);
  }
}
```

The pizza blueprint is now describing two **methods** (`constructor`and `addTopping`)

Any pizza created wtih the Pizza class/blueprint will have these properties and methods. 

Methods will exist on instances created from the class, but not on the class itself. Eg: addTopping() method can be called on pizza1 (or any instance of Pizza), but cannot be called on the Pizza class itself. 

---
### Introduction to `constructor `
---
`constructor` is a special method that is executed when an object instance is created from a class

This is where we can set up the default state for new instances (default values for new object's properties)

#### Customizing the Constructor

Every class can have ONE constructor method - we can use this to setup any default property values for an object

Back to our pizza example:
```javascript
class Pizza {

  constructor(size, crust) {
    this.size = size;
    this.crust = crust;
    this.toppings = ["cheese"];
  }

  addTopping(topping) {
    this.toppings.push(topping);
  }

}
```

With the constructor above, we can pass in the size and crust type as parameters when we create a new instance of pizza:

```javascript
let pizza = new Pizza('medium', 'deep dish');
```

And when the pizza is created, it'll look like this:
```javascript
let pizza = {
  size: 'medium',
  crust: 'deep dish',
  toppings: ["cheese"]
}
```

---
### JavaScript and OOP vs Functional Programming
---
Look back at the ToDo List assignment (involved making a function that created new to-do list objects)

We could have solved this problem using a class (OOP), but JS also allows us to use functions to solve the problem (FP). Cool!

In purely OOP languages (eg. Ruby), we can ONLY solve the problem with classes

---
### Primitives as Objects
---

Each primitive in JS (except symbols - has their own rules) has  a corresponding object constructor

```javascript
typeof(true); 
// "boolean" 
typeof(Boolean(true)); 
// => "boolean" 
typeof(new Boolean(true));
// => "object"
```
As seen above, object constructor can be invoked with keyword `new`

When we call object constructors, we create a new unique instance of the object requested

When we use an object constructor to create a primitive, we can run into issues with comparing primitives

eg
```javascript
const greeting = "Hello, world!" 
const objGreeting = new String("Hello, world!");

greeting == objGreeting; 
// => true

greeting === objGreeting; 
// => false
```
The object string is not strictly the same as the primitive string (despite having same content), but can be coerced into equality if using the `==` operator. 

> For this reason, it's considered BAD PRACTICE to use object constructors to create primitives!

