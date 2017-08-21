# Algo
Aggressive Algorithm Practice 



```javascript
1) Best Usage of filter() in JS:

function findElement(arr, func) {
  var longWords = arr.filter(func);
  return longWords[0];
}
findElement([1, 3, 5], function(num) { return num % 2 === 0; });



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
  
  
# 4) Filter vs Every vs hardcode 

https://www.freecodecamp.org/challenges/everything-be-true

~~~

function truthCheck(collection, pre) {

 var l= collection.filter(o => o[pre]);
 console.log(l);
  if(l.length===collection.length)
  return true;
  else return false;}
truthCheck([{"name": "Pete", "onBoat": true},
{"name": "Repeat", "onBoat": true, "alias": "Repete"}, 
{"name": "FastFoward", "onBoat": NaN}], "onBoat")
~~~

OutPut:

~~~

[ { name: 'Pete', onBoat: true },
  { name: 'Repeat', onBoat: true, alias: 'Repete' } ]
=> false
~~~

Every

~~~
function truthCheck(collection, pre) {
 return collection.every(o => o[pre]);
}
truthCheck([{"name": "Pete", "onBoat": true},
{"name": "Repeat", "onBoat": true, "alias": "Repete"}, 
{"name": "FastFoward", "onBoat": NaN}], "onBoat")
~~~

Hard code (except NAN which is not matched when compared)

~~~ 
function truthCheck(collection, pre) {
  // Is everyone being true?
 var l= collection.filter(o => o[pre]===false || o[pre]=== 0 ||o[pre]=== NaN || o[pre] === undefined || o[pre]=== null ||o[pre]=== ""  );
 console.log(l);
  if(l.length>0)
  return false;
  else return true;}

truthCheck([{"name": "Pete", "onBoat": true},
{"name": "Repeat", "onBoat": true, "alias": "Repete"}, 
{"name": "FastFoward", "onBoat": NaN}], "onBoat")
~~~

output 

# is true??? should be false because of NAN


5) Codewars Questions: CamelCase function

~~~

function camelCase(string){
  return string.replace( /^\w|(\s\w)/g, a=>a.toUpperCase()).replace(/\s/g,'');  // replace(/\s/g,'') removes spaces
}
camelCase("123 hello how are you ");

~~~

6) concat two arrays and remove duplicates


function sym() {
console.log(arguments[1]);


//concat two arrays
var arr = arguments[0].reduce(function(a, b) {
  return a.concat(b);
}, arguments[1]);
console.log(arr);

//remove duplicates in concated array 
 arr = arr.filter( function( item, index, inputArray ) {
           return inputArray.indexOf(item) == index?console.log("y",inputArray.indexOf(item),index): console.log("n",inputArray.indexOf(item),index);
    });
return arr;
}
sym([5, 2, 1, 4],[1,2, 3]);

7) Symmetric difference

function sym(args) {
var arr = Array.prototype.slice.call(arguments);
  return arr.reduce(function(acc, item){
       console.log( "\n acc.filter(val => !item.includes(val))\n", acc.filter(val => !item.includes(val)),"\nitem.filter(val => !acc.includes(val))\n",item.filter(val => !acc.includes(val)),"\n");
   
    acc  = acc.filter(val => !item.includes(val)).concat(item.filter(val =>    !acc.includes(val))).sort(); // removes similar elements ;
    
        return acc.filter( function( item, index, inputArray ) {
           return inputArray.indexOf(item) == index;   //removes duplicate values;
    });
    
  }, []);

}
sym([1, 2, 3], [5, 2, 1, 4]);


output: 
 acc.filter(val => !item.includes(val))
 [] 
item.filter(val => !acc.includes(val))
 [ 1, 2, 3 ] 


 acc.filter(val => !item.includes(val))
 [ 3 ] 
item.filter(val => !acc.includes(val))
 [ 5, 4 ] 

=> [ 3, 4, 5 ]
   
 
8)
 var count=0;
function steamrollArray(arr) {
  // I'm a steamroller, baby
 
  return arr.reduce(function(acc,item){
    if(Array.isArray(item)){
  console.log("if  :acc",acc,"item",item,"concat",count++)
    return acc.concat(steamrollArray(item));}
    console.log("\nelse :acc",acc,"item",item,"concat",count++)
    return acc.concat(item);
  }, [])
  
  return arr;
}

steamrollArray([1, [2], [3, [[4]]]]);

Output:


else :acc [] item 1 concat 0
if  :acc [ 1 ] item [ 2 ] concat 1

else :acc [] item 2 concat 2
if  :acc [ 1, 2 ] item [ 3, [ [ 4 ] ] ] concat 3

else :acc [] item 3 concat 4
if  :acc [ 3 ] item [ [ 4 ] ] concat 5
if  :acc [] item [ 4 ] concat 6

else :acc [] item 4 concat 7
=> [ 1, 2, 3, 4 ]

https://forum.freecodecamp.org/t/using-array-prototype-reduce-to-reduce-conceptual-boilerplate-for-problems-on-arrays/14687
