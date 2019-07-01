---
{
  "name": "Creating a Store",
  "slug": "creating-a-store",
  "visibilityLevel": 2,
  "draftMode": false
}
---
Notice anything interesting? We haven't actually installed `redux` yet! We've mostly just written plain ol' JavaScript. All that `redux` is going to do is offer us a few helper functions. Let's install it now, if we haven't already:

`npm install redux`

Now it's time to hook everything up to our central command—the `store`. The store contains the object representing the state of our application (accessible via `store.getState`), and contains the only method capable of changing that state (`store.dispatch`). 

* [Create a store](http://redux.js.org/docs/basics/Store.html) in your `store.js` file using your reducer. 
* `export default` your created store.

<hint title="Full solution">
![Full Solution](https://learndotresources.s3.amazonaws.com/workshop/5a7a11b64df85500040c20ff/storejs.png)
</hint>

<guide>
You've created a store using your reducer and exported it from store.js
</guide>