---
{
  "name": "AddGrocery Component",
  "slug": "addgrocery-component",
  "visibilityLevel": 2,
  "draftMode": false
}
---
The last component we will need for now is the `AddGrocery` component. Its characteristics are:

- It renders a form field and a button
- It controls the form input value.
- It expects an `add` callback function to come as props, and when the user clicks the button (or hits `Enter`), the callback will be invoked with the value the user typed.


Here's the source code:

```js
import React, { Component } from "react";

class AddGrocery extends Component {
  constructor(props) {
    super(props);
    this.state = {
      input: ""
    };
    this.handleKey = this.handleKey.bind(this);
  }

  handleKey(evt) {
    if (evt.key === "Enter") {
      this.props.add(this.state.input);
      this.setState({ input: "" });
    }
  }

  render() {
    return (
      <div className="add-grocery">
        <input
          type="text"
          value={this.state.input}
          onChange={evt => this.setState({ input: evt.target.value })}
          onKeyDown={this.handleKey}
        />
        <button
          onClick={() => {
            this.props.add(this.state.input);
            this.setState({ input: "" });
          }}>
          Add Grocery
        </button>
      </div>
    );
  }
}

export default AddGrocery;
```

**Another important thing to notice** is that this component has state and the input field is controlled. When using Redux, it is not required that ABSOLUTELLY ALL pieces of state live in the store - you can still have local state in your React components. 

The rule of thumb is: Global state (state that is important to multiple parts of your application) should be kept in the Redux Store. Local state (state that isn't needed anywhere else, it's small and only used in a single component) can be kept in React Component State.

In this case, only the **TEMPORARY** values that the user types in the field are kept in the component state. As soon as the user clicks on "Add Grocery" or hits `Enter`, the final typed value will be added to the Redux Store.

This was the last React Component we needed to add to the project. If you start the server and open the app in its current condition, you should be able to see all the components and type on the form field, but nothing else works: we cannot add items to the grocery list, we can't check them as "bought" etc. Let's make things work by integrating the App and its state to a Redux Store.