---
{
  "name": "App Component",
  "slug": "app-component",
  "visibilityLevel": 2,
  "draftMode": false
}
---
We will keep the `app.js` module really simple: Change the file to render some markup (including an image file) as well as three other components: `AddGrocery`, `GroceryList` and `Footer`.

Here's the final source code - make sure you understand it, then go ahead to copy and paste it to your project.

---
**Copy & Paste** - Yeah, we usually instruct you to avoid copying and pasting code during workshops. In this case, though, we will make an exception: We want you to get familiarized with all the React components, but we don't want to waste your time re-typing a component when the important parts of this exercise are interacting with Redux.

In short: Go on and copy/paste all React components to your project, but make sure you understand these components

---

```js
import React from "react";
import Footer from "./Footer";
import AddGrocery from "./AddGrocery";
import GroceryList from "./GroceryList";

const App = () => (
  <div className="app">
    <img src="groceries.png" alt="Groceries" width="500" />
    
    <div className="list">
      <AddGrocery />
      <GroceryList />
      <Footer />
    </div>
  </div>
);

export default App;
```

Obviously these components don't exist yet (they're currently just blank files), so let's start from the bottom and create the `Footer` component next.