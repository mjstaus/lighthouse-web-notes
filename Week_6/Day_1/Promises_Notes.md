## Promises Notes

### Promise States
---
1. Fulfilled(Resolved) - It worked, action related to the promise succeeded
2. Rejected - It didn't work
3. Pending - Still waiting!
4. Settled - Either fulfilled or rejected
  - A promise can only settle once, so you can only have 1 resolved/rejected statement!

### Promise Workflow
---
The space between promise being created and being settled is STILL ON THE MAIN THREAD and therefore potentially BLOCKING

So they're not a pass for safely executing long-running time functions!

Rather, they help decide what *will* happen when the async operation settles

Think of promises as a try/catch wrapper around an async operation that will finish at an unknown time

### Syntax
---

```javascript

new Promise(function(resolve, reject){
  const value = 'do something'
  if(somethingWentWropng){
    reject(value)
  } resolve(value)
})
```

Always 2 parameters/callbacks for the function inside of promise
1. Resolve
2. Reject

These give you the ability to explicitely state what constitutes resolution vs rejection for the promise

eg. 
```
img.onload = resolve;
img.onerror = reject;
```

What next?
```javascript

new Promise(function(resolve, reject){
  const value = 'do something'
  if(somethingWentWropng){
    reject()
  } resolve(value)
}).then(function(value){
  //success! Value passed from promise into next function
  return nextThing(value);
}).catch(rejectFunction);
//error handler. Since there's no argument passed into reject(), this function receives undefined
```

If the value that's passed is another promise, then that promise will execute FIRST and then whatever value it resolves to gets passed on to the next link in the chain

So:
1. Resolve -> value passes to next .then
2. Reject -> value passes to next .catch
