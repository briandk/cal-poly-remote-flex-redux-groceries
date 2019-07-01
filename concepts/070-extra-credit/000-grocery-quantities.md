---
{
  "name": "Grocery Quantities",
  "slug": "grocery-quantities",
  "visibilityLevel": 2,
  "draftMode": false
}
---
<img src="https://learndotresources.s3.amazonaws.com/workshop/5a7a11b64df85500040c20ff/bananas-oranges.png" width="374">


Ok, from this list I know I need to buy Bananas and Oranges, but how much of each? Your next task is to update the redux store to include a quantity for each grocery item (starting at 1 when the item is added), as well as:

* Creating a `SET_QUANTITY` action type
* Creating a `setQuantity` action creator
* Updating the reducer to produce a new state when an action of type `SET_QUANTITY` is dispatched.

Finally, update the GroceryItem to display the current quantity as well as letting the user update it:

<img src="https://learndotresources.s3.amazonaws.com/workshop/5a7a11b64df85500040c20ff/withquantity.png" width="374">
