---
{
  "name": "Testing it Out",
  "slug": "testing-it-out",
  "visibilityLevel": 2,
  "draftMode": false
}
---
We don't have any components dispatching `ADD_GROCERY` yet, but let's temporarily dispatch it a couple of times manually to experience what we've set up so far and check if you have wired up everything correctly.

In the bottom of your `store.js` file, add:

![manual dispatches](https://learndotresources.s3.amazonaws.com/workshop/5a7a11b64df85500040c20ff/testing.png)


Run `npm start`, open the browser and you should see the grocery list propulated with "Milk" and "Cookies"

Everything good? Ok, remove these manual dispatches and let's properly connect the `AddGrocery` component next.