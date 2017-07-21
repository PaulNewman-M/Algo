# Algo
Aggressive Algorithm Practice 

Best Usage of filter() in JS:

~~~

function findElement(arr, func) {
  var longWords = arr.filter(func);
  return longWords[0];
}
findElement([1, 3, 5], function(num) { return num % 2 === 0; });

~~~

^Link: https://www.freecodecamp.org/challenges/finders-keepers 
