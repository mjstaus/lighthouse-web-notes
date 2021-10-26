## Objects Notes

### Objects Review:
* Contain key-value pairs (each key maps to a value)
* Object keys are unique (can't have same key twice in one object)
* Keys are strings
* Values can be any type

### Object Literals
Literals in JS are constant values that can be assigned to variables. They are syntactic representations of data (eg. "string", [array], etc.)

Objects have literal syntax of {}

```javascript
const me = {
  firstName: "Martha",
  eyeColour: "blue",
  hairColour: "red",
}
```
### Object Values
* Can be of any type (eg. string, boolean, number, etc)
* *Can* be undefined, but this is not typically done (as explained more below)

### Accessing Object Values
* Use square bracket notation when value is dynamic

```javascript
const myFirstName = me["firstName"]

//get the value associated with key "firstName" on object "me"
```

* Key *must* be in " " , otherwise will be considered a variable
* If a variable points to a key, then we can use that variable in square bracket notation without " ":
```javascript
const propertyName = "firstName";
const firstName = me[propertyName];
```
* We can also use dot notation to access object values:
```javascript
const myFirstName = me.firstName
```
* If we try to access an object key that doesn't exist, we'll get ```undefined```
  * This is why we don't want to use undefined as a value!

### Assigning a New Value to a Key

* Use square bracket notation:
```javascript
me["hairColour"] = "blonde"
```

### Objects as Values

Values don't have to be primative types. We can nest object and arrays inside objects:

```javascript

const me = {
  firstName: "Martha",
  eyeColour: "blue",
  hairColour: "blonde",
  educationHistory: {
    elementarySchool: "Notre Dame Elementary",
    highSchool: "Seaquam Secondary",
    university: ["McGill University", "University of British Columbia"]
  }
}
```
Square bracket notation can access nested values:
```javascript
me["educationHistory"]["highSchool"]; //"Seaquam Secondary"
```
* To inspect an object's keys, use Object.keys(object)
```javascript
Object.keys(me); // ['firstName', 'eyeColour', 'hairColour', 'educationHistory']
```

### Objects and Iteration

To iterate over an object ```{key:value}```, we need to use a ```for...in``` statement

Example (from LHL):
```javascript
const planetMoons = {
  mercury: 0,
  venus: 0,
  earth: 1,
  mars: 2,
  jupiter: 67,
  saturn: 62,
  uranus: 27,
  neptune: 14
};
```
We can iterate over planetMoons and access the keys (planet) and values (planetMoons[planet])

```javascript
for (let planet in planetMoons) {
  let numberOfMoons = planetMoons[planet];
  console.log("Planet: " + planet + ", # of Moons: "+ numberOfMoons);
}
```
**Note:** 
For...in can sometimes produce unexpected results if object has properties inherited from prototype chain as well as method names (I DONT KNOW WHAT THIS MEANS YET). 
Additional filtering is sometimes necessary:
```javascript 
for (let planet in planetMoons) {
  // additional filter for object properties:
  if (planetMoons.hasOwnProperty(planet)) {
    //  ...
  }
}
```
#### Further Reading:
Stack Overflow:
https://stackoverflow.com/questions/684672/how-do-i-loop-through-or-enumerate-a-javascript-object

MDN Docs:
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in




