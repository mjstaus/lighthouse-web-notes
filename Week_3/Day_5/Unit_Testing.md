## Intro to Automated Testing
---
###  Unit Testing
---
- Testing small pieces of code (eg. individual functions) alone and isolated
- Does NOT include external resources (eg. databases)
- Typically involves giving the function some inputs and checking that the outputs are correct
- Popular tools for unit testing: Mocha, Jasmine, Tape

---
### Integration Testing
---
- Test how parts of the system work together
- Useful for situations where unit testing isn't enough (need to test multiple systems TOGETHER, or a complex piece of code where unit testing doesn't cut it)
  - In the 2nd case (complex code), it's better to change the code so that unit testing could be used intead of integration testing!
- Might require set-up or configuration (eg. making a test database) -> means integration tests are harder to set up and maintain than unit tests

---
### Functional Testing
---

- AKA E2E testing, browser testing
- Testing of complete functionality of an application. (Eg. in a web app, might involve using a tool that clicks around the pages to test the application)
- Used for testing common user interactions
- Need to be careful not to make these tests too "fine-grained"
- Popular tool: Selenium
  - Selenium usually run with Selenium WebDriver or Protractor


>Notes from https://codeutopia.net/blog/2015/04/11/what-are-unit-testing-integration-testing-and-functional-testing/