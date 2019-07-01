---
{
  "name": "Action Creators",
  "slug": "action-creators",
  "visibilityLevel": 2,
  "draftMode": false
}
---
Now that we have an action type defined in our `store.js`, let's make use of that type in what is known as an *action creator*.

The difference between an action type and creator can often become skewed. _Action types_ are a label for a kind of action. _Action creators_ are functions that can (possibly) take information and return objects that are formatted to be sent into the reducer. These objects are called *actions* (thus having been created) and always have a `type` property that describe what *type* of action they are.

* In `store.js`, write and export a function named `addGrocery`, which will receive a string (the name of the item), and returns an object with three properties:
  * `type`, which should be equal to our `ADD_GROCERY` constant
  * `id`, which is a number incremented sequentially
  * `text`, which should be equal to the string that was passed into the function.

**Note:** _Everything besides the `type` is often referred to as the `payload` of the action._

```js
let nextId = 0;
export const addGrocery = (text) => (
  {
    type: ADD_GROCERY,
    id: nextId++,
    text
  }
);
```

This is a function that returns an object (returning is implicit here because we're using an arrow function).

<guide>
You've correctly defined and exported the action creator.
</guide>