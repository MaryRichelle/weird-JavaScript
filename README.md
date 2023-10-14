# Weird 🙄 behavior of Coolest JavaScript

```js
var amount = 42
console.log(amount)
```

why its weird 😵

- console.log(......) command has to implicitly coerce the *number 42* value to a *string* value type  to print it out

- javascript work on the right side of = *assignment operator* and then assign that value to left hand side

***

```js
b *2
```

why its weird 😵
a standalone *expression statement* is not very useful and common as it will not have any effect on running the program it would retrieve the value of of b and multiply it by 2 but than wouldn't do anything with the result. which means javascript will run line by line will execute this expression and move to next line but if we want to use it we can store it in a variable and use it (that's weird 🙄)
***

```js
 console.log( typeof null) 
 ```

why its weird 😵?  
typeof null is "object" (that's weird 🙄)
even null is primitive value in but type of null is object
***
***

```js  
const num = () =>{

return 9;
};

console.log(num() < 10); // true
```

num function returns 9 which is less than 10  
***

```js
console.log(1..toString() === "1");// true (that's weird 🙄)
```

why its weird 😵?  

- floating point 1.0
- .toString()
- first . is for floating point 1.0  

***

```js
const value = "123abc";
const result = Number(value);

console.log(typeof result);// "number" 
```

***

```js
function fun(a, b, c) {
return b + c
}
fun(5, 3, "wowwwwww", "this is so cool") // '3wowwwwww' string concatenation 
```

***

## Operators / Operator Precedence

```js
console.log(-4 + 3 + "8") // -1 + "8" === 18 
console.log("A" - 1); // NaN
console.log(2 + "-2" + "2"); // 2-22
console.log("Hello" - "World" + 78); NaN
console.log("Hello"+ "78"); "Hello78"
console.log(5 + "5"); // "55"  
console.log(5 - "5"); // 0 
```

***

```js
let x = 9;
console.log(x)
let y = x++; // y= 9 x= 10 (that's weird 🙄) postfix increment operator
console.log({x}) // 10
console.log({y}) // 9
let z = ++x// 11
console.log({x}) // 11
console.log({z}) // 11
console.log(z *  y) 
; // 11* 9 (that's weird 🙄) prefix increment operator
```

why its weird 😵?  

- **x++ the increment operator increments and returns the value before incrementing.** on line ``let y = x++`` x  current value is returned and  assigned to y and than it increment
- **++x the increment operator increments and returns the value after incrementing.** x is increment before its value is return

***

```js

let a = 5;
let b = a++; //a = 6, b= 5 (that's weird 🙄)
let c = ++a; // a = 7, c = 7 (that's weird 🙄)

let result = a + b + c; // 19

console.log(result);
```

***

```js
console.log(4 + (5 - - 4) - - 5)// 18 ==> () have hight precedence ⬇️
```

1:(5 - - 4) => 5 +4 => 9  
2: 4 + 9 => 13  
3: 13 - - 5 => 13 + 5 => 18 // Operator precedence  
***

```js
console.log([10]+[10]); // "1010"
console.log([10]+[10,10]); //'1010,10'
console.log([1, 2] + [3, 4]);// 1,23,4 

```

why its weird 😵?  

because of + operator array are coerced to strings "10" , "10,10" (that's weird 🙄)  
***

```js
let x=10 ; 
let y='hello';
console.log(Number('5'+x));//  output : 510 (that's weird 🙄)
console.log(`The result ${y} and`+ false); // 'The result hello andfalse'
```

why its weird 😵?
  string concatenation because of + operator with typeof number and string accordingly  

***

```js

function display()  
{  
  console.log("10"+(20+30));  // "1050" Operator precedence for () 
  console.log("10"+20+30); // "102030"
  console.log(10+20+"30") // "3030"

}  
display();  
```

why its weird 😵?  
 string concatenation because of +  and Operator precedence
 1: ()
 2: + operator

***

## logical && and ||

```js

true; // true
false; // false"
!true; // false
!false; // true

true && true; // true ===> if test is true print the value of 2nd
true && false; //  false ===> if test is true print the value of 2nd
false && true; // false ===> if the test is false print the value of 1st one
false && false; // false
  
true || true; //   true ===> if the first  test is true prints the value of first
true || false; // true ===> if the first  test is true prints the value of first
false || true; // true ===> if the first  test is false prints the value of 2nd one
false || false; // false ===> if the first  test is false prints the value of 2nd one
```

***

```js
const array = [1, 2, 3];
let result = 0;
for (const value in array) {
  // console.log(value) 0,1,2,
result += +value; // 3 ==> append operator add 1 to its previous index as its iterating over indexes but ```+value``` +(unary Operator: it covert string to number) didnt make any difference its already a number
}
console.log(result)
```

## == and === operators

- number comparison

```js

42 == "42" // true ==> with loose equality implicit type coercion happened on one or both value to make of some type "24" coerced to number  
"24" === 24 //false no type coercion
```

- boolean comparison

```js
"42" == true // false  ==>  with == boolean converted to numbers (true = 1, false = 0) thus 
"42" == 1 // false ==> == type coercion happens and 
42 == 1 // false ==> values are not same

```

**Reminder** `Never compare  boolean(true or false) any other type of value with  ==`

- NaN

```js
NaN == NaN// false
NaN === NaN // false
"1" == NaN // false
"1" === NaN // false
5 === NaN // false
42 == NaN // false
false === NaN // false
true == NaN // false
```

NaN is never equal to any other value and to it self NaN it will return false
**loose equal and strictly equal  treats NaN as unequal to every other value**

```js
  let a = []
  let b = []
  console.log(a == b) // false 
  console.log(a === b)// false
```

- objects are held by reference both `==` and `===` check  only if the reference match not the content/value so both are false

***

### Implicit Type Coercion

```js

let a = 0;
let b = false;
console.log((a === b));// false ===> type coercion not allowed
console.log((a == b)); //true ===>  
//1 because of == type coercion happen   
//2  boolean coerced to  number but when    
//3 false coveted to number it become 0 and true converted to 1
// but if 
let c  = 41;
console.log((c == b)); // false


```

***

```js

let a=[]
let b=""
console.log(a==b) // true ==> with == loose equal array are coerced to string
```

why its weird 😵?  
loose equal  == converts  one or both values to same type and [] is converted to ""

***

```js
let a = "52";
let b = 52
a === b // false
// (that's weird 🙄)
a ==b // true 
typeof (a==b); // boolean


```

true because type coercion happens behind the walls javascript  tries to convert the type of one of the operand of == operator to match them  and *a* "52" becomes 52

with === the coercion is not allowed  
***

```js
true != 1;  // false (that's weird 🙄)  
true !== 1; // true (that's weird 🙄)
```

 with Inequality != operator  type coercion occurs  true becomes 1 and its false
 !== Strict Inequality operator type coercion is not allowed true and 1 are not same
 ***

### Hoisting

```js
console.log(x); // undefined
var x = 5;
 ```

- variable declaration and function declaration(with function keyword) are hoisted
 in this snippet of code because of hoisting ```var x``` (variable declaration ) is taken at the top of the scope where its undefine because its value is not initialized yet and we initialize the value with initializer =

***

```js
var employeeId = '1234abe';
(function(){
console.log(employeeId);// undefined 
var employeeId = '122345';
})();
```

why its weird 😵?  
inside IIFE it is undefined because of hoisting  moves  variable at the top of the scope and at the point var employeeId is just declared but not yet initialize (that's weird 🙄)
yes it didnt go to global scop since it find employeeId inside function scop
***

```js
  console.log(a) // undefined ===> var a is hoisted in global scop
  var a;
  function foo(){
  console.log(a) // undefined ===> looking in global scop where a is undefined 
  }
  foo()
  a = 1
  console.log(a) // 1
```

but if

```js
console.log(a) // ReferenceError: a is not defined because of let 
  let a;
  ```

***

```js
var x = 23;
(function(){
var x = 43;

  (function random(){
    // x is hoisted here but undefined
    x++; // undefined++ 
    console.log(x); // NaN 
    var x = 21; // x = 21 initialized
})();

})();


```

## Array and Array Methods

```js
const arr = [1, 2, 3];
arr[5] = 6;
console.log(arr.length); //6 with two empty spaces
```

***

```js
const arr = [1,2,3,4,5,5,,6]
const a= arr.map((x,y)=> x+y)
 console.log(a)// [ 1, 3, 5, 7, 9, 10, <1 empty item>, 13 ]
```

***

```js
function myFun(){
var arrayNumb = [2, 8, 15, 16, 23, 42];
arrayNumb.sort();
console.log(arrayNumb);// [ 15, 16, 2, 23, 42, 8 ] 
const prices = ["a", "b", "f", "e", "d","c"];
prices.sort();
console.log(prices);// ["a","b","c","d","e","f"]
}
myFun()
```

why its weird 😵?  
one that sorts an array in place and sort method with out argument  reacts on elements of array  as string and sort them in dictionary order (lexicographic ) (that's weird 🙄)

***

```js
let v =[56,67,21,78,(1,2,3),(4,5,6)];
let [a,b,...c]  = v
console.log(c); // [ 21, 78, 3, 6 ]
console.log(a)//56
console.log(b)//67

```

***

```js

var greet = 'Hello World';
var toGreet = [].filter.call(greet, function(element, index) {
return index > 5;
});
console.log(toGreet);
```

***

```js

a = [1, 2, 3]
b = a // reference to a as array are pass by reference
a = a + [4] // 1,2,34 both a(reference to a) and [4]converted to string and concat
console.log(b) // [1, 2, 3] a was assign to b before it changes it values on a = a + [4]
```

(that's weird 🙄)
***

```js

 const arr = [1,2,3,4,5,5,,6]
 const a= arr.slice()
 console.log(a) // [ 1, 2, 3, 4, 5, 5, <1 empty item>, 6 ]
```

***

```js

let numbers = [1, 2, 3, 4, NaN];
console.log(numbers.indexOf(NaN), typeof numbers[numbers.length-1], number[-1] )// -1 ,"number" 'undefined'
```

***

## Recursion

```js

function test(x){
if(x > 0){
test(x-1)// Recursion function runs until x > 0 but every time function runs x-1
}
console.log(x)// 0 1 2 3 4 5
}
let data = 5
test(data);
```

why its weird 😵?

***

## Objects

```js
const props = [
{ id: 1, name: "John"},
{ id: 2, name: "Jack"},
{ id: 3, name: "Tom"}
];
const [, , { name }] = props; 
console.log(name); "Tom"
```

first two objects are skipped and ```{ id: 3, name: "Tom"}``` is destructed ```{name}``` thus  name = Tom

***

```js
const obj1 = { a: 0 };
const obj2 = Object.assign({}, obj1);

obj1.a = 2;
console.log(obj1, obj2);// { a: 2 } { a: 0 }
```

why its weird 😵?  
obj2 have all the the value of it and add new obj1 so its { a: 0 }  
later obj1 value of property a was changed but not in the obj2
***

***

```js
let x= {}, y = {name:"Ronny"},z = {name:"John"};
x[z] = {name:"Jene"};
x[y] = {name:"Jenney"};// assigning a property/key y with value {name:"Jenney"} to variable x (which is empty object)    
// x['object Object'] = {name:"Jenney"} OR

console.log(x[y]); // {name:"Jenney"}

```

1: objects can be used as keys  
2: object literals are not copied, they point to same memory location  
3: ojects coerced to strings when they are passed as keys  

```js
 x = {
  "[object Object]": { name:"Jenney"}
};
```

in the end, you have an object x with a single property where the key is the string "[object Object]", and its value is {name:"Jenney"}
***

```js
// TODO ===> need more attention here 
  let hero = {
      powerLevel: 99,
      getPower(){
      return this.powerLevel;
    }
  }
  let powerOfHero = hero.getPower;
  let hero2 = {powerLevel:42};
  console.log(powerOfHero());//undefined
  console.log(powerOfHero.apply(hero2)); //42
```

***

```js
  const someFunction = function(){
    console.log(this); //global/ window object 
    const b = {
      func1: function(){
      console.log(this); //b object
      }
  }
  const c = {
    func2: ()=>{
    console.log(this); // window because of arrow function 
    }
  }
  b.func1();
  c.func2();
  }
 someFunction();

```

```js
var set = new Set();
set.add("+0").add("-0").add(NaN).add(undefined).add(NaN);
console.log(set);
/*Set(4) {  
  '+0',  
  '-0',   
  NaN,  
  undefined   
  }*/

```

## this keyword

```js
function myFunc(){
console.log(this.message);// undefined
}//(that's weird 🙄)
myFunc.message = "Hi John";// setting a property to function 
myFunc()
```

why its weird 😵?  
but properties in function are not directly accessible
***

```js
  const b = {
    name:"John",
    itsFun : function(){
      var self = this;
      console.log(this.name); // "John"

        (function(){
          console.log(this.name); // undefined 
          console.log(self.name); // "John"
        })();

      }
  }
  b.itsFun();

```

***

## Scope and Closure

```js
for (var i = 1; i <= 5; i++) {
  setTimeout(function timer() {
    console.log(i)///6 6 6 6 6(that's weird 🙄)  
  }, i * 1000)
}
```

because of var i is global  
setTimeout because of its async behavior  decide to run after    ```i * 1000```  time so the
for loop started to execute but when its ```i = 5``` code runs condition meet but before the loop ends ```i++``` which is now 6 so in the scope of loop ```i = 6``` and condition false ```i !<= 5``` i = 6 resides in the global scope for setTime out  
when set time out run it triggers the i which is 6 for 5 times with execution of loop
***

```js
  (function(a){
    return (function(){
      console.log(a);// 45 ===> because of Closure inner function have access to parent function
      a = 23;
    })()
  })(45);

// Simpler ⬇️
  function outer(a){
    return function inner(){
    console.log(a)
      a = 23;
      console.log(a)
    }
 }
 const parent = outer(45)
 parent()


```

***

```js
function bigFunc() {
  let newArray = new Array(700).fill('♥');
  return (element) => newArray[element];
}
let getElement = bigFunc(); // Array is created only once
getElement(599);
getElement(670);
// without Closure ⬇️
  function bigFunc(element){
    let newArray = new Array(700).fill('♥');
    return newArray[element];
    }
    console.log(bigFunc(599)); // Array is created on every function call
  console.log(bigFunc(670));
```

***

```js
  function randomFunc(){
  for(let i = 0; i <= 5; i++){
    (function(){
        let j = i
      setTimeout(()=>console.log(j),1000)// 0 ,1 , 2 , 3 , 4 ,5
      })()  
    }
  }
 const fun =  randomFunc();
 

  function randomFunc(){
    for(let i = 0; i <=5; i++){
      setTimeout(()=> console.log(i),1000);// 0 ,1 , 2 , 3 , 4 ,5 
    }
  }
  randomFunc();

```

because of let declaration block scope  
***

## async js

```js
setTimeout(()=>{console.log("second")},0)
console.log("first")

```

"first"  
"second"
set time out  is Asynchronous  
***

```js

console.log("hello");

setTimeout(() => console.log("world"), 0);

console.log("hi");


```

(that's weird 🙄)  
"hello"  
"hi"  
"world"  
why its weird 😵?
setTimeout is async function and it give space to other code to execute first even  it set to 0

***

```js
function randomFunc(){
for(var i = 0; i < 2; i++){
setTimeout(()=> console.log(i),1000); // 2 ,2
}
}
randomFunc();


```

var i is global variable when set time out run after the loop it triggers 2 from the value of i before condition false

```js
function someFun(){
setTimeout(()=>{
console.log(x); // 2 
console.log(y); // 12
},3000);
var x = 2;
let y = 12;
}
someFun()
```

because setTimeout as a async function it give space to rest of the code(as its going to wait for 3`) and entire function executes  from top to bottom lets say setTimeout is now before the closing } of someFun and after x and y declaration and initialization
***

```js
(function(){
setTimeout(()=> console.log(1),2000);
console.log(2);
setTimeout(()=> console.log(3),0);
console.log(4);
})();
```

output is  
2  ===> executes immediately  
4  ===> executes immediately  
3  ===> runs after 0 seconds had to give place to rest of the code  
1 ===> runs after 3 seconds  
***

Javascript is not yet done......  
 continue...
 (that's weird 🙄)
