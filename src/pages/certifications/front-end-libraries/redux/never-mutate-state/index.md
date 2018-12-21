---
title: Never Mutate State
---
## Never Mutate State

The key here is creating a new Array from the initial state and adding the new todo (passed as a property of action) to the list. There are a few ways to do this, but arguably the two best are below:

* Using the spread operator(...):
```javascript
const immutableReducer = (state = todos, action) => {
  switch(action.type) {
    case ADD_TO_DO:
      // don't mutate state here or the tests will fail
return [...state, action.todo]; // this is the line you'll edit
    default:
      return state;
  }
};
```
Note: this is only available in ES6 or later.

* Using the concat method:
```javascript
return state.concat(action.todo);
```
