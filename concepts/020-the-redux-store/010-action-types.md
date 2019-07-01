---
{
  "name": "Action Types",
  "slug": "action-types",
  "visibilityLevel": 2,
  "draftMode": false
}
---
Let's think about the actions that a user can take to change the UI. We can define them with a set of string constants called `action types`. This is a really great aspect of using Redux, although it will seem very strange and unnecessary at first. All the possible events that will affect what is eventually our global Redux state are given a name; this is what we call an `action type`.

Say we wanted to have a button for a user to order all items in the grocery list. We might define an action as `const PLACE_ORDER = 'PLACE_ORDER';`. (By convention, string constants are stored in a variable in ALL CAPS.)

Our current goal is for the Redux store to handle our grocery items array, so let's define an action that represents adding a grocery to the array:

* In `store.js`, let's add the following line:

```js
const ADD_GROCERY = 'ADD_GROCERY';
```

That's pretty clear! We've now defined the first type of action that can be sent to and received by our Redux state. All future action types will be defined in an identical fashion. 

Next, we'll use this type in an action creator...

<hr/>

**You may be wondering:** why bother making a constant to hold the string? Why not just write the string whenever you need it? The most important reason is that it makes errors much easier to debug. If you mis-type a constant, chances are you'll get a ReferenceError in runtime, and your linter will probably yell at you. However, if you misspell a string, you won't get any errors at all; you'll be completely on your own to figure out where you went wrong.

<guide>
You've added the line above to `store.js`
</guide>