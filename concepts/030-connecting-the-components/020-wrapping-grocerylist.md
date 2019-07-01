---
{
  "name": "Wrapping the GroceryList Component",
  "slug": "wrapping-grocerylist",
  "visibilityLevel": 2,
  "draftMode": false
}
---
Open `GroceryList.js` and import `connect` from `react-redux`.

The GroceryList component doesn't make any dispatches, so you will only need a function to map state (from the store) to props.

<hint title="Additional guidance">
* Create a `mapStateToProps` function that returns an object with one key: `groceries`. The value of groceries comes from the redux store's state.
* Invoke `connect` with your `mapStateToProps` function. The return value from invoking connect is a Higher Order Component.
* Invoke the Higher Order Component passing the `GroceryList` as parameter.
* Don't forget to update the `export` in this module - We will not export `GroceryList` anymore, but the result of invoking the Higher Order Component. 
</hint>


There won't be any noticeable changes yet, but your code should look similar to the code in this hint:


<hint title="Solution Code">
![GroceryListContainer](https://learndotresources.s3.amazonaws.com/workshop/5a7a11b64df85500040c20ff/Screen%20Shot%202018-03-27%20at%203.19.36%20PM.png)
</hint>