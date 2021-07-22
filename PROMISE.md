
# JavaScript Promises


```loadData(url, callback)```

Example:

Prior to ES6 you would use an anonomus function to handle data requests. This is what would introduce our code to an other theory of call back hell. Every new API request would expext another callback function. 

```function setup() {
  some function here
  loadData(someAPI, function(data) {
   handle data here
  ) loadData(anotherAPI, function(data) {
   handle different API data here
  )
  } ```

```function setup() {
  some function here
  loadData(someAPI, gotData)
  } ```
  
 
