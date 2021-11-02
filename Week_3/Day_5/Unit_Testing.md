## Unit Testing

---
### Behaviour Driven Development (BDD)
---
> Plan = Specify the *behaviour* of your app  in terms of **user stories** which are broken down into **scenarios** that can be built and tested

#### BDD Frameworks:
- Every test involves setting up some data, running some code, then asserting whether or not the code did what it was supposed 

#### Setting Up:

We need a testing framework! We'll be using:
1. **Mocha** (testing framework)
2. **Chai** (assertion library)

>Note on Chai:
>- Testing in console: must ```require('Chai')```
>- Testing in browser: must NOT include ```require('Chai')```

---
The following sections are notes from https://www.sitepoint.com/unit-test-javascript-mocha-chai/

---



#### Directory Structure
---

Put your tests in a separate directory from your main code files. 

```test/moduleTest.js```

---
#### Test Runner
---

This is needed if testing in the browser. I'm going to skip this for now (testing in node), but read more here later:

https://www.sitepoint.com/unit-test-javascript-mocha-chai/

---
#### Test Building Blocks
---

1. ```describe``` Block
```javascript
describe('array', function() {
  // Test code goes here
});
```
  - Describe is used to group individual tests
  - First parameter ('Object' above) = what we're testing
2. ```it``` Blocks
```javascript
describe('array', function() {
  it('should start empty', function() {
    // Test implementation goes here
  });

  // We can have more its here
}); 
```
  - ```it``` is used to create the actual tests
  - First parameter gives description of the test (human-readable)
    - In example above "it should start empty" tells us that we should start with empty array
  - Code to implement the test goes into the function (2nd parameter of ```it```)
  - Each ```it``` should explain ONE specific behaviour

---
#### Writing the Test Code
---

For the example above, we need to create an array and then test that it's empty:

```javascript

const assert = chai.assert;

describe('Array', function() {
  it('should start empty', function() {
    const arr = [];
    assert.equal(arr.length, 0);
  });
});
```
