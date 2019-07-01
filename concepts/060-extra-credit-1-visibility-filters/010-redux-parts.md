---
{
  "name": "Redux Parts",
  "slug": "redux-parts",
  "visibilityLevel": 2,
  "draftMode": false
}
---
## Action Type & Action Creator

You will begin by creating a new action type `SET_VISIBILITY_FILTER` and a new `setVisibilityFilter` action creator.

The `setVisibilityFilter` action creator expects a parameter that determines what to filter. Possible values are 'SHOW_ALL', 'SHOW_BOUGHT' and 'SHOW_ACTIVE'. (You might consider creating constants for those values).


## Updating the reducer

Next, you need to modify the reducer. You will need to:
- Add a new key in the initial state for the default value of `visibilityFilter`. (It should start as 'SHOW_ALL')
- Add a new `case` in your `switch` statement to deal with the `SET_VISIBILITY_FILTER` action.

<guide>
You created a new constant for the action type `SET_VISIBILITY_FILTER`
You created a `setVisibilityFilter` action creator.
You added a new key to the reducer initial state: `visibilityFilter` (starting with some option such as 'SHOW_ALL')
You added a new `case` statement to update the `visibilityFilter` key in the reducer.
</guide>