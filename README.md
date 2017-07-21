# Algo
Aggressive Algorithm Practice 

1) Best Usage of filter() in JS:

~~~

function findElement(arr, func) {
  var longWords = arr.filter(func);
  return longWords[0];
}
findElement([1, 3, 5], function(num) { return num % 2 === 0; });

~~~

Link: https://www.freecodecamp.org/challenges/finders-keepers 


2)

https://www.freecodecamp.org/challenges/drop-it

~~~
function dropElements(arr, func) { // Drop them elements.
var r; var t=arr.length; 
for(var j=0;j<t;j++){ 
  // console.log("j=",j) 
  if(arr[0]>=3)               // same as func(arr[0]  but doesn't works.
  {break;} else{ arr.shift(); } } 
  return arr;
  } 
  dropElements([0,1,0,1], function(n) {return n >=3; });
  
  ~~~
  
  
  ~~~
  :beginner: Basic Code Solution:
function dropElements(arr, func) {
  // drop them elements.
  var times = arr.length;
  for (var i = 0; i < times; i++) {
    if (func(arr[0])) {
      break;
    } else {
      arr.shift();
    }
  }
  return arr;
}

// test here
dropElements([1, 2, 3, 4], function(n) {return n >= 3;})

~~~
  
  
  
  
  

