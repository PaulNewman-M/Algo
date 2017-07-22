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
  
.....
  
  
3)

https://www.freecodecamp.org/challenges/binary-agents

~~~

function binaryAgent(str) {
  var array=[];
  var s=[];
  array=str.split(" ");
  for(var j=0;j<array.length;j++)
  {var sum =0;
    var n=array[j].split("");
    var l=array[0].length;
    for(var i=--l,k=0;i>0;i--,k++){
    sum +=n[i]*Math.pow(2,k);
}
  s.push(  String.fromCharCode(sum));

  }
  
  return s.join("");
}

binaryAgent("01000001 01110010 01100101 01101110 00100111 01110100 00100000 01100010 01101111 01101110 01100110 01101001 01110010 01100101 01110011 00100000 01100110 01110101 01101110 00100001 00111111");

~~~

~~~
function binaryAgent(str) {
  biString = str.split(' ');
  uniString = [];

/*using the radix (or base) parameter in parseInt, we can convert the binary
  number to a decimal number while simultaneously converting to a char*/

  for(i=0;i < biString.length;i++){
    uniString.push(String.fromCharCode(parseInt(biString[i], 2)));
  }
  
  // we then simply join the string
  return uniString.join('');
}

// test here
binaryAgent("01000001 01110010 01100101 01101110 00100111 01110100 00100000 01100010 01101111 01101110 01100110 01101001 01110010 01100101 01110011 00100000 01100110 01110101 01101110 00100001 00111111");

~~~

~~~
:rotating_light: Advanced Code Solution:
function binaryAgent(str) {
  return String.fromCharCode(...str.split(" ").map(function(char){ return parseInt(char, 2); }));
}

// test here
binaryAgent("01000001 01110010 01100101 01101110 00100111 01110100 00100000 01100010 01101111 01101110 01100110 01101001 01110010 01100101 01110011 00100000 01100110 01110101 01101110 00100001 00111111");
~~~

~~~
***Functional Programming: ***
function binaryAgent(str) {
  let array = str.split(' ');
  array = array.map(item=>{return String.fromCharCode(parseInt(item,2));});
return array.join('');
}
binaryAgent("01000001 01110010 01100101 01101110 00100111 01110100 00100000 01100010 01101111 01101110 01100110 01101001 01110010 01100101 01110011 00100000 01100110 01110101 01101110 00100001 00111111");
~~~
  
  

