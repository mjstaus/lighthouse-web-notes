## OOP Part 3: Super
---
### Method Overriding and Super
---

What if we want a subclass to have similar but *slightly different* behaviour to its superclass?

Method Overriding = when a subclass implements a method that already exists in the superclass

However, this might result in some duplicate code

---
### Use `super`
---

Use keyword `super` to call superclass method within the subclass method

Basicall, `super` allows us to access the superclass

Like so:

```javascript
class Dog {
  constructor(name, age, color){
    this.name = name
    this.age = age
    this.color = color
  }
  boopSnoot() {
    return "Boop!"
  }
};

class Chi-spaniel extends Dog {
  parent1: "chihuahua"
  parent2: "spaniel"

  boopSnoot() {
    return `${super.boopSnoot()} You are the world's cutest dog!`
  }
};
```
