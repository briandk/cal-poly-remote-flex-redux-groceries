---
{
  "name": "Setting Up React-Redux",
  "slug": "setting-up-react-redux",
  "visibilityLevel": 2,
  "draftMode": false
}
---
The first step is installing `React-Redux`:

```bash
npm install react-redux
```

Next, make sure to wrap all your components in a Provider component - The Provider component will make the Redux store available to the connect() calls in the component hierarchy below.

You will want to add the Provider to the upmost level of your component hierarchy, so go on and add the Provider component.

<hint title="Need more information?">
Again, add it somewhere close to the top of the component hierarchy. A good choice would be on the `client/index.js` file
</hint>

<hint title="Solution code">
![provider](https://learndotresources.s3.amazonaws.com/workshop/5a7a11b64df85500040c20ff/Screen%20Shot%202018-03-27%20at%203.07.51%20PM.png)
</hint>