## Refactoring

### Look for Patterns and Minimize Duplicate Code
---
  eg. Loopy Lighthouse Refactor (from Pseudocode W1/M1):
  ```javascript
  for (const num of nums) {
  let output = "";

  if (num % 3 === 0) {
    output += "Loopy";
  }
  if (num % 4 === 0) {
    output += "Lighthouse";
  }
  console.log(output === "" ? num : output);
}
```
Compare above to prep-module work!

