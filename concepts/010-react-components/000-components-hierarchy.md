---
{
  "name": "Components hierarchy",
  "slug": "components-hierarchy",
  "visibilityLevel": 2,
  "draftMode": false
}
---
The first step in building a React application is usually breaking down the interface into nested components. Remember that components should be small and have a single concern. In other words, a component should ideally only do one thing. If it ends up growing, it should be broken into smaller subcomponents.

If we apply this concept to the Groceries List app, we will come to the following composition:

![Component Diagram](https://learndotresources.s3.amazonaws.com/workshop/5a7a11b64df85500040c20ff/groceries_diagram.png)

## Building the Components
Having figured out the interface hierarchy, it’s time to build the components. Yes, the focus of this workshop is on **Redux**, but because it's important that you are very familiar with the components in your React application before doing any Redux-related work, you will create each one of these components over the next steps (technically you will basically copy and paste their source codes - but this will help understand what they are doing).

To get started, create empty files for each component we will build inside the `/client/components` folder (`AddGrocery.js`, `GroceryList.js`, `GroceryItem.js` and `Footer.js`)

<hint title="Creating empty files using the Terminal">
  <terminal>
  touch client/components/AddGrocery.js client/components/GroceryList.js client/components/GroceryItem.js client/components/Footer.js
  </terminal>
</hint>
