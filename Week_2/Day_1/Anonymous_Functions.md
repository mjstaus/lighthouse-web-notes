## Anonymous Functions

So far, the functions we've been working with have all been named and assigned to a variable...but they don't need to be!

**ANONYMOUS FUNCTIONS** = Functions NOT named/assigned to a variable

Callback functions are often not named/assigned to a variable, and are often written inline:
```javascript
findWaldo(["Alice", "Bob", "Waldo", "Winston"], function(index) {
  console.log("Waldo is located at:", index);
});
```
*(example from LHL)*

The function above is not named, nor assigned to a variable. It is called by findWaldo (or more generally, by the function that it's passed into)


>The receiving function that contains the anon function will give that parameter a name, so we can just declare the anon function while it's being passed into the receiving function.

IT'S OK THAT YOURE CONFUSED RIGHT NOW. 

Example refactored where's waldo function with inline anonymous function:

```javascript
const findWaldo = (names, found) => {
  names.forEach(name => {
    if (name === "Waldo") {
      found(names.indexOf(name));
    }
  });
};

findWaldo(["Alice", "Bob", "Waldo", "Winston"], function(index) { console.log(`Found Waldo at index ${index}!`)});
```


