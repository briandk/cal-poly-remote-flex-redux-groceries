---
{
  "name": "The Reducer",
  "slug": "reducer",
  "visibilityLevel": 2,
  "draftMode": false
}
---
Now we need to describe how our state will change when it receives an action. With plain React, we use `setState`. With Redux, we pass an `action` to the store's `dispatch` method, and the store executes its `reducer` function. The reducer function has the following signature:

```js
const reducer = (prevState, action) => {
  return newState;
}
```

We pass in the state we're about to replace with the effect of an action, and the object we return describes the new state our app will use to re-render.

Typically, the reducer consists of a `switch` statement that describes a different update depending on the action's type. In this case, we have one expected action -- `ADD_GROCERY`. If the `action.type` is not `ADD_GROCERY`, we should just return the state before action.

**REMEMBER**: it is EXTREMELY important that the reducer be a *pure function*. This means you must follow two rules:
1. The same output is always returned for the same input
2. No side effects (AJAX, mutating data, etc).

We'll see more reasons why this is so important later, but for now think of it this way: our state is the crux of our app, so any changes to it should be as predictable and debuggable as possible.

### Your turn:

In the `store.js` file, write a reducer function that:

1. Starts with the initial state of `{ groceries: [] }`
2. Expects to receive an action with the `ADD_GROCERY` type.
3. When it receives an action with the `ADD_GROCERY` type, it then should:
    - Build a new grocery item with the action payload (`id` and `text`), plus a `bought` property starting as `false'
    - Append the new grocery item to the groceries array in an immutable fashion (returning a new array instead of mutating the original one)
    - Return a **new state object**.

<hint title="Solution">
```js
const initialState = { groceries: [] };

function reducer (state = initialState, action) {
  switch (action.type) {
    case ADD_GROCERY:
      const newGrocery = {
        id: action.id,
        text: action.text,
        bought: false
      };
      return { ...state, groceries: [...state.groceries, newGrocery] };
    default: 
       return state;
  }
}
// Two things to note: 
//   1. We use spread operator (...) to maintain immutability.
//   2. If we receive an action that doesn't have a type we recognize, we return 
//      the previous state.
```
</hint>

<guide>
You've defined the reducer described above
</guide>