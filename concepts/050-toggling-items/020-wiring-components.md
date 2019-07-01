---
{
  "name": "Wiring the React Components",
  "slug": "wiring-components",
  "visibilityLevel": 2,
  "draftMode": false
}
---
The redux pieces are all in place: If a `TOGGLE_GROCERY` actions is dispatched, the grocery will be marked as "bought". 

Now we need to update the React components to dispatch that action, starting with the `GroceryList` (and its `GroceryListContainer`). 


### `GroceryList`

The grocery list should expect to receive a `toggleGrocery` function via props - Make sure that each `GroceryItem`'s `onClick` calls the `toggleGrocery` function with its ID. 

In other words, what we want is that when a `GroceryItem` get's clicked, it will invoke `toggleGrocery` with that item's id:

![updated grocery list](https://learndotresources.s3.amazonaws.com/workshop/5a7a11b64df85500040c20ff/updated_grocerylist.png)

But where is the `toggleGrocery` function coming from? Well, the container component created by `connect` will provide it:


### `mapDispatchToProps`

Currently, the connect function in `GroceryList.js` only uses a `mapStateToProps` function. Create a `mapDispatchToProps` function.
`mapDispatchToProps` will return an object with the key `toggleGrocery` and the value being a function that expects an grocery item ID as parameter and dispatches the toggleGrocery action. (Don't forget to import the `toggleGrocery` action creator).