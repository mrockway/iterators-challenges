# Solutions

## each

```js
// `each` takes in an array and a callback function
var each = function(list, callback) {
  // iterates through each item in array
  for (var i = 0; i < list.length; i += 1) {
    // calls callback function with item and index
    callback(list[i], i);
  }
  // returns original array
  return list;
};
```

## map

```js
// `map` takes in an array and a callback function
var map = function(list, callback) {
  var mappedList = [];
  // iterates through each item in array
  for (var i = 0; i < list.length; i += 1) {
    // calls callback function with item and index (adds result to `mappedList`)
    mappedList.push(callback(list[i], i));
  }
  // returns mapped array of results
  return mappedList;
};
```

## reduce

```js
// `reduce` takes in an array of numbers
var reduce = function(numList) {
  var sum = 0;
  for (var i = 0; i < numList.length; i += 1) {
    sum += numList[i];
  }
  return sum;
};
```

## truthTest

```js
function filter(arr, truthTest){
  var outputArr = [];
  for (var i=0; i<arr.length; i++){
    if truthTest(arr[i]){
      outputArr.push(arr[i]);
    }
  }
  return outputArr;
}
```

## partition

```js
function partition(arr, truthTest){
  var trueArr = [];
  var falseArr = [];
  for (var i=0; i<arr.length; i++){
    if truthTest(arr[i]){
      trueArr.push(arr[i]);
    } else {
      falseArr.push(arr[i]);
    }
  }
  return [trueArr, falseArr];
}
```

## pluck

```js
function pluck(arr, key){
  var outputArr = [];
  for (var i=0; i<arr.length; i++){
    outputArr.push(arr[i][key]);
  }
  return outputArr;
}
```

## where

```js
function where(arr, properties) {
  var outputArr = []

  // loop through keys in properties
  for (var key in properties) {
    for (var i = 0; i < arr.length; i++) {
      var obj = arr[i]

      // if values are the same and obj is not already in outputArr
      if (properties[key] === obj[key] && outputArr.indexOf(obj) === -1) {
        // push obj into outputArr
        outputArr.push(obj);
      }
    }
  }
  return outputArr;
}
```