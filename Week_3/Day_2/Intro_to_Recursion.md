## Introduction to Recursion

Loops are great and all, but you don't HAVE to loop. Some languages don't even have for or while loops! 

Recursion is an alternative to loops! 

For example -  Counting even numbers from 0 to 12:
1. Traditional Loop
```javascript
let number = 0;
while (number <= 12) {
  console.log(number);
  number += 2;
}
```
2. Recursion
```javascript
1.| function countEvenToTwelve(number) {
2.|   if (number <= 12) {
3.|     console.log(number);
4.|     countEvenToTwelve(number+2);
5.|   }
6.| }
7.| countEvenToTwelve(0);
```

WHAT HOW IS THE FUNCTION CALLING ITSELF? 

Recursion = function calls itself in a loop!

In the example above, the function calls itself until number <= 12. Each time in runs, the parameter is increased by 2 (instead of incrementing the number directly like in a for loop)

> WARNING: Make sure you include some sort of exit condition or it will keep calling itself forever

Example:
```javascript
function countUpFrom(number) {
  console.log(number);
  countUpFrom(number+1);
}
countUpFrom(1);
```
Output = Will count to ~17000, then crash with message ```RangeError: Maximum call stack size exceeded.``` (AKA **stack overflow**)

**Recursive Case** = If true, function will continue to call itself (eg. number <= 12)

**Base Case** = function will not call itself if true (eg. number >12)

> In a properly designed recursive function, the input gets closer and closer to the **base case** with each recursive call. 

A function must have at least one recursive case and at least one base case in order to be recursive!

### When to Choose Recursion Over Iteration
If the problem you're trying to solve is a *smaller version* of the larger problem you've already solved, then recusion is likely a better choice!

>Note: Recursion often comes up in tech interviews!!

### Summary

- Recursion is when a function calls itself until it doesn't
- Any iteration problem can be solved by recursion (and vice versa)
- Recursion is a type of *control flow*

Don't worry that you're not comfortable yet! It'll come with practice 🤗🌱