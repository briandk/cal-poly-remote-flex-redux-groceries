---
{
  "name": "Wiring the Redux parts",
  "slug": "wiring-redux",
  "visibilityLevel": 2,
  "draftMode": false
}
---
### Action Type & Action Creator

You will begin by creating a new action type and action creator:

In the `store.js` file, create a new constant for toggling items:

```js
const TOGGLE_GROCERY = 'TOGGLE_GROCERY';
```

In sequence, create a new action creator that return an action of the type TOGGLE_GROCERY. This action creator should receive an grocery id as parameter and add it to the action payload.

<hint title="Action Creator solution code">
![toggle grocery action creator](https://learndotresources.s3.amazonaws.com/workshop/5a7a11b64df85500040c20ff/Screen%20Shot%202018-02-08%20at%203.25.45%20PM.png)
</hint>

### Updating the reducer

Next, you need to modify the reducer to deal with the TOGGLE_GROCERY action.
When this action gets dispatched, you need to update the grocery with the specific ID matching the action payload to have it's `bought` toggled.

<hint title="reducer solution code">
<code><pre style="color: white;">
case TOGGLE_GROCERY:
  const groceries = state.groceries.map(grocery => {
    if (grocery.id === action.id) {
      return {...grocery, bought: !grocery.bought};
    } else {
      return grocery;
    }
  });
  return {...state, groceries};
</pre></code>

<br /><br />

Also notice that this conditional can be shortned by using a ternary expression:

<br />

<img src="https://learndotresources.s3.amazonaws.com/workshop/5a7a11b64df85500040c20ff/toggle_reducer_ternary.png" />

</hint>
