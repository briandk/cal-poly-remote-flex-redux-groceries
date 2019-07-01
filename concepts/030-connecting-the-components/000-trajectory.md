---
{
  "name": "Trajectory",
  "slug": "trajectory",
  "visibilityLevel": 2,
  "draftMode": false
}
---
Now that we have our Redux store in place, let's bring React into the picture.

Remember that it's preferable to keep the majority of our React components small and limit interaction with the outside world - they should just receive props and render stuff. They're what we call "Presentational" components.

Container components (or connected components), on the other hand, are React components that we use to talk to the outside world (make Ajax requests, subscribe to a redux store etc) and render the presentational component (while supliying it with props). They are just plain React components as well, but it keeps the project more organized as they act as a bridge between your components and Redux. So, for every component we have in our project that needs to integrate with the Redux store, we will create a container component. 

Of course we won't create each connected component by manually creating React Components, subscribing to the store and etc. Instead, we will use `React-Redux`'s `connect` function to generate these container components for us.

The trajectory for the next few steps is:

* Use the `connect` method to create a Higher Order Component to wrap the `GroceryList` component. It should map the array of groceries from the store to props passed down to the `GroceryList` component.
* Use the `connect` method to create a Higher Order Component to wrap the wrap the `AddGrocery` component, providing a prop to let it dispatch an `ADD_GROCERY` action.

<guide>
You have read and understood the above
</guide>