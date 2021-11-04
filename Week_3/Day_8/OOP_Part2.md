## OOP Part 2: Instances

---
### Introduction to Inheritance
---


What if we have multiple classes which share *some* properties, but not all? 

We don't want to have duplicate code, but we can't just use the same class because of the differences...

---
### Solution with Inheritance
---

Using inheritance means building a new class based on an existing class

1. Create a class with all the properties that are SHARED by the sub-classes
```javascript
class Dog {
  constructor(name, age, color){
    this.name = name
    this.age = age
    this.color = color
  }
  boopSnoot() {
    console.log("Boop!")
  }
}
```

2. Create sub-classes that `extend` the parent class
```javascript
class Chi-spaniel extends Dog {
  parent1: "chihuahua"
  parent2: "spaniel"
}
```

Now we have a general Dog class, and a Chi-spaniel class that inherits behaviour and state from Dog class while also having its own particular behaviour and state!
