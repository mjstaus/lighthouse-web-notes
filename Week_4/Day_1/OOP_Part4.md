## OOP Part 4: Getters and Setters
---
### Getters and Setters
---
- Getters = method used to GET value of a property
- Setters = method use to SET value of a property

Example:
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

  setSize(size) {
    this.size = size;
  }
  getSize() {
    return this.size;
  }
}

// DRIVER CODE
const pizza = new Pizza();
pizza.setSize('m');
pizza.getSize(); // m
```

BUT...why don't we just access `pizza.size` directly??

Two reasons:
1. Validating data before assigning to a property
2. Computing a value instead of pulling from a property

---
### Validating Data 
---
What if someone tried to set their pizza size to a size that doesn't exist? That would be bad! We need to validate their size request before assigning it as a value!

```javascript
class Pizza {

  // ...

  // setSize now includes data validation
  setSize(size) {
    if (size === 's' || size === 'm' || size === 'l') {
      this.size = size;
    }
    // else we could throw an error, return false, etc.
    // We choose here to ignore all other values!
  }
}

// DRIVER CODE
let pizza = new Pizza();
pizza.setSize('s');
```
---
### Computed Value
---
Let's say we want to assign a price to our pizza based on how many toppings have been added. 
```javascript
class Pizza {

  // ...

  getPrice() {
    const basePrice = 10;
    const toppingPrice = 2;
    return basePrice + (this.toppings.length * toppingPrice);
  }
}

// DRIVER CODE
let pizza = new Pizza();
pizza.getPrice();
```

---
### Getters and Setters using `get` and `set`
---

```javascript
class Pizza {

  // ...

  // replace our custom getters / setters with these ones!
  get price() {
    const basePrice = 10;
    const toppingPrice = 2;
    return basePrice + this.toppings.length * toppingPrice;
  }

  set size(size) {
    if (size === 's' || size === 'm' || size === 'l') {
      this._size = size;
    }
  }
}
```

We've replaced our method names with keywords `get` and `set`

The difference is that we can now access price and size as VALUE properties instead of METHOD properties

```javascript
pizza.price;  //instead of pizza.getPrice()
pizza.size = 's'; //instead of setSize('s')
```

Much cleaner!

Here, price and size are BOTH functions AND values. 

What's happening under the hood? `get` and `set` syntax binds an object's property to a function that will be called when that value is looked up.

This syntax isn't necessary to get the job done, but can create much nicer interface for developers to work with :)




