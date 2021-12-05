## Event Propagation
---
How events move through the DOM

---

### Bubbling and Capturing

Events that impact child elements *bubble up* through its parents

We can stop an event's propagation using ```stopPropagation()```

Almost all events bubble! 
Exceptions:
- focus

The element where the event STARTED is called the **target element**
- We can access the target element with ```event.target```

Stop Bubbling:
- An event will bubble all the way up to the document object, or even to the window. All handlers in the path will be called as the event bubbles to the surface
- We can use ```stopPropagation()``` on any handler in the path! The handler on which it calls WILL also be triggered
- To stop upward propagation AND prevent handlers on current element from running, use ```event.stopImmediatePropagation()```