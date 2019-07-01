---
{
  "name": "GroceryList and GroceryItem Components",
  "slug": "grocerylist-and-groceryitem-components",
  "visibilityLevel": 2,
  "draftMode": false
}
---
The `GroceryList` component is responsible for showing a list of grocery items. But since each grocery item contains its own functionality (they can be clicked, they can appear with a strike-through line...), we will also make a `GroceryItem` component to encapsulate this functionality:

## `GroceryItem.js`

Here's the source code for the `GroceryItem` component:

```js
import React from "react";

const GroceryItem = ({ onClick, bought, text }) => (
  <li
    onClick={onClick}
    style={{
      textDecoration: bought ? "line-through" : "none"
    }}>
    {text}
  </li>
);

export default GroceryItem;
```

A few things to notice in the code above:

1. It expects three props: `onclick`, `bought` and `text`. 
1. The `bought` and `text` props are used to display the item and its styling.
1. The `onClick` prop needs to be a function, and is directly passed to the `li` element `onClick`. In practice, this means that whatever function you provide to <GroceryItem **onClick**> will be invoked when the user clicks on the item.


## `GroceryList.js`

The `GroceryList` component expects a list of `groceries` as props, then maps over then to create the `GroceryItems`:

```js
import React from "react";
import GroceryItem from "./GroceryItem";

const GroceryList = (props) => (
  <ul>
    {props.groceries.map(grocery => (
      <GroceryItem key={grocery.id} {...grocery} />
    ))}
  </ul>
);

export default GroceryList;
```

**Note**: For now, go back to the `<GroceryList>` component in `App.js` and add a `groceries` prop, initializing it to an empty array.  We'll change that, later.

Notice the `{...grocery}` pattern on line 7 - React components support the usage of the spread operator (`...`) inside component tags, and it literally means “Copy all properties from the `grocery` object and pass them down as individual props”. 
In other words, if a grocery object look like this:

```js
{ id: 1, text: "Milk", bought: false },
```

Using the spread syntax, it would be as if we passed down all props manually to the GroceryItem component.

This:

```js
<GroceryItem key={grocery.id} {...grocery} />
```

Becomes this:

```js
<GroceryItem key={1} id={1} text="Milk" bought={false} />
```