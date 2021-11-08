## Intro to Asynchronous Programming
---

In async programming, a unit of code runs separately from the main thread of the program and then notifies the program when it's finished

So far, we've been doing *synchronous* programming - a single thread that runs in order

The problem here is that if we need to run code that is time consuming, then the rest of the code is blocked from running until the first part completes

---
### Asynchronous Callbacks
---
Javascript uses async callbacks to deal with time consuming tasks!
