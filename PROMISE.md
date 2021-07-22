
# JavaScript Promises


```loadData(url, callback)```


Prior to ES6 you would use an anonomus function to handle data requests. This is what would introduce our code to an other theory of call back hell. Every new API request would expext another callback function. Another reason for callback issues are handling errors and successes.

Example:

```
    function setup() {
    some function here
    loadData(someAPI, function(data) {
    handle data here
    ) loadData(anotherAPI, function(data) {
      handle different API data here
      )
   } 
```
  _____

```
  function setup() {
    some function here
    loadData(someAPI, gotData)
  } 
```
  
______

As of ES6 we can handle our data as a promise. This promise is a javaScript object that can return as fulfilled, pending, rejected. 

Checkout [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) for more details on promises.

```
  let promise = fetch(url)

```

We also get introduced to an element called .then(). It is a method that handles the data once it has been fulfilled. There is also a method called .catch to handle any data in the instance the data is rejected. 
