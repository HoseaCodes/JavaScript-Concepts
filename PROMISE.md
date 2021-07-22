
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

## Fetch API

As of ES6 we can handle our data as a promise. This promise is a javaScript object that can return as fulfilled, pending, rejected. 

Checkout [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) for more details on promises.

```
  let promise = fetch(url)

```

We also get introduced to an element called .then(). It is a method that handles the data once it has been fulfilled. There is also a method called .catch to handle any data in the instance the data is rejected. 

Once a promise is fulfilled you recieve a JSON object. The .json() method also returns a promise. 

```
    fetch(url)
        .then(response => response.json())
        .then(data => console.log(data))
        .catch(err => console.log(err.message))
```

## Chaining Fetch Requests

In order to continue making request based off of our initial call we would need to chain the request. To chain the request you must return the desired fetch. 

```

    fetch(url)
        .then(response => response.json())
        .then(data => {
            handle new data as desired
            return fetch(anotherURL+data.word)
        ))
        .then(response => response.json())
        .then(data => console.log(data))
        .catch(err => console.log(err.message))
```

## Async & Await

Often called syntax sugar. Essentially it does the handle the promises differently but it displays the code in a more legible way.


```
    async function getData() {
        let response = await fetch(url)
        let json = await response.json()
        let response2 = await fetch(anotherURL+data.word)
        let json2 = await response.json2()
        
        return {
            data: json.data,
            data2: json2.data
        }
     }
```
