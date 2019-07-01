---
{
  "name": "Logging Middleware",
  "slug": "logging-middleware",
  "visibilityLevel": 2,
  "draftMode": false
}
---
As you know, Redux's `createStore` function accepts middleware as its second argument. 

Your task is to add a logging middleware - you can either provide your own custom logging middleware of use a popular one like `redux-logger`:

* `npm install --save redux-logger`
* `import loggerMiddleware from 'redux-logger'`
* import the `applyMiddleware` helper function from Redux
* `applyMiddleware` accepts middleware as any number of arguments; pass `loggerMiddleware` into `applyMiddleware`

Now, go back and refresh the page. Add a few items to dispatch the `ADD_GROCERY` action. Check out your console. You will now see logging output for every action that is sent to the store, as well as information about the previous/next states. Pretty cool, right?

<guide>
You've completed the steps above and examined console output
</guide>