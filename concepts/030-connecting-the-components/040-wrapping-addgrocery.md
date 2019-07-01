---
{
  "name": "Wrapping the AddGrocery Component",
  "slug": "wrapping-addgrocery",
  "visibilityLevel": 2,
  "draftMode": false
}
---
By now you know the drill: We will use `connect` to wrap the `AddGrocery`:

* Import the `connect` function (as well as the `addGrocery` action creator) into `AddGrocery.js`.
* The `AddGrocery` won't use any piece of state from the store - it will only dispatch (in other words, no need for `mapStateToProps`).
* Create a `mapDispatchToProps` function. It should return an object with one key: `add`. This key should point to a function that dispatches the action creator.
* `connect` always expects the parameters in order: The first one maps **state** to props, the second one maps **dispatches** to props. Since we are not mapping any state for this component, pass `null` as the first paramenter.
* Update the `export` in this module.

Your code should look similar to the code in this hint:

<hint title="Solution Code">
```js
function mapDispatchToProps (dispatch) {
  return {
    add: function (text) {
      dispatch(addGrocery(text));
    }
  };
}

export default connect(null, mapDispatchToProps)(AddGrocery);
```
</hint>

Notice that the `AddGrocery` component expects a prop named "add".

Now you should be able to add new items to the grocery list. 

<guide>
You can add new items to the grocery list app.
</guide>