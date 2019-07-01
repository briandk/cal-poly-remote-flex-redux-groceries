---
{
  "name": "Redux Devtools",
  "slug": "redux-devtools",
  "visibilityLevel": 2,
  "draftMode": false
}
---
This section is a bonus, but a very small and easy one, and one which may yield some nice dividends as you start working with Redux!

Go ahead and install the [Redux DevTools Chrome extension](https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd?hl=en).

Then, as per [the instructions here](https://github.com/zalmoxisus/redux-devtools-extension#11-basic-store), modify your new store so that it is "instrumented" with these tools. 
NB: the plus sign is just github's way of showing that a line has been added in a diff (which is also why the line is colored green). Deleted lines are red and prepended with a minus sign. 
Make sure you haven't actually copied the plus sign at the beginning of the line over or your JS engine will try to coerce the return value of `window.__REDUX_DEVTOOLS_EXTENSION__()` into a number before passing it into the `createStore` method, and you're gonna have a bad time.

You'll know it's working if you open your Chrome dev tools, click on "Redux," and see a full UI (instead of the message "no store found").

<guide>
You refresh your Redux Groceries tab, and the Redux dev tools pane in Chrome does NOT say "No store found."
</guide>