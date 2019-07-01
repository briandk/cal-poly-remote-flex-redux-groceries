---
{
  "name": "React Components",
  "slug": "react-components",
  "visibilityLevel": 2,
  "draftMode": false
}
---
### GroceryList

Update the `mapStateToProps` function in your `GroceryList.js` file. Instead of passing ALL `state.groceries` down as props, you should filter them based on the current `visibilityFilter`.



### Footer

Now comes the final piece: Add links to the footer component and wrap it using the `connect` function to dispatch changes to the visibilityFilter.