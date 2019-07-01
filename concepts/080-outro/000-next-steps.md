---
{
  "name": "Review",
  "slug": "next-steps",
  "visibilityLevel": 2,
  "draftMode": false
}
---
We've covered a lot today, and learned a lot of new vocabulary. Let's take a moment to review:

<h5>Glossary of Terms</h5>
* **Action**: an object that has *at least* a "type" field, and any other fields needed to calculate the change to the state
* **Action Creator**: a function that returns an action. We write these to help us stay DRY
* **Action Type**: a string constant describing something that will cause the UI to update
* **Reducer**: a function that we write for each app, which accepts the previous state from the Redux store as its first argument, and an action as its second argument. It should return a new state object with the changes described by the action. The reducer should be a pure function - there should be no side effects, and it should not mutate the previous state
* **Store**: an object created by the "createStore" function from Redux. It accepts a reducer that we write and maintains a "state" object internally (which we have access to via "store.getState"). When we pass an action to "store.dispatch", the store swaps out its current state with the result of invoking the reducer with the action and the current state. We can also register listeners via "store.subscribe", which the store will invoke after the state has changed

## Connecting react and redux with react-redux

At a high level, the `connect` method **connects specific parts of the redux store to react components** as props.

&emsp;&emsp;&emsp;REDUX: STORE MANAGES STATE&emsp;&emsp;&emsp;REACT-REDUX&emsp;&emsp;&emsp;REACT: COMPONENTS DISPLAY UI
<br>
&emsp;&emsp;&emsp;State & Dispatch (updates state)&emsp;----->&emsp;`connect` to&emsp;----->&emsp;render(props) => view

### Separating concerns

The `connect` method introduces a layer of separation between the state management logic and presentational logic, meaning our presentational react components doesn't need any awareness of redux whatsoever; any data a react component needs will always be received through props. Even if you do away with redux one day, your presentational components will remain untouched as long as you use another tool that connects your new state manager to your react app.

&emsp;&emsp;&emsp;NEW STATE MANAGEMENT TOOL&emsp;&emsp;SOME OTHER CONNECTER&emsp;&emsp;&emsp;**REACT: COMPONENTS DISPLAY UI**
<br>
&emsp;&emsp;&emsp;State & State updater&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;--------->&emsp;connects to&emsp;--------->&emsp;&emsp;&nbsp;&nbsp;**render(props) => view - UNCHANGED!**

### Targeted updates

Further, `connect` allows you to cherry-pick the parts of state that your react component should be connected to. `connect` will only pass new props to your component if the relevant pieces of state are *referentially distinct*. That's why it's especially important to respect immutability in redux state - if you accidentally mutate a part of state, your react component *will not* be made aware of such changes through `connect`.