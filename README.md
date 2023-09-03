# Weird 🙄 behavior of Coolest JavaScript

```js
var amount = 42
console.log(amount)
```

why its weird 😵

- console.log(......) command has to implicitly coerce the *number 42* value to a *string* value to print it out

- javascript work on the right side of = *assignment operator* and then assign that value to left hand side

***

```js
let a = "52";
let b = 52
a ==b // true 
typeof (a==b); // boolean
a === b // false
// (that's weird 🙄)
```
true because type coercion happens behind the walls javascript  tries to convert the type of one of the operand of == operator to match them  and _a_ "42" becomes 42

with === the coercion is not allowed  
***

```js
true != 1;  // false (that's weird 🙄)  
true !== 1; // true (that's weird 🙄)
```

 with Inequality != operator  type coercion occurs  true becomes 1 and its false
 !== Strict Inequality operator type coercion is not allowed true and 1 are not same
 ***

``` js
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
const arr = [1,2,3,4,5,5,,6]
const a= arr.map((x,y)=> x+y)
 console.log(a)// [ 1, 3, 5, 7, 9, 10, <1 empty item>, 13 ]
```

***

```js
var employeeId = '1234abe';
(function(){
console.log(employeeId);// undefined 
var employeeId = '122345';
})();
```

why its weird 😵?  
it is undefined because of hoisting  moves  variable at the top of the scope and at the point var employeeId is just declared but not yet initialize (that's weird 🙄)

***
What is the output of this code?

```js
let x = 9;
let y = x++; // y= 9 x= 10 (that's weird 🙄)
console.log(++x *  y) ; // 11* 9 (that's weird 🙄)
```

why its weird 😵?  
on line *let y = x++* x is incremented after its current value is assigned to y
<!-- increment on the right side of assignment operator = value of x increase by 1 but 1 and than its assign to y so the value of x is 10 and y = 9  -->

***

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

let a = 5;
let b = a++; //a = 6, b= 5 (that's weird 🙄)
let c = ++a; // a = 7, c = 7 (that's weird 🙄)

let result = a + b + c; // 19

console.log(result);
```

***

```js
function myFun(){
var arrayNumb = [2, 8, 15, 16, 23, 42];
arrayNumb.sort();
console.log(arrayNumb);// [ 15, 16, 2, 23, 42, 8 ] 
const prices = ["a", "b", "f", "e", "d","c"];
prices.sort();
console.log(prices);
}
myFun()
```

why its weird 😵?  
one that sorts an array in place and sort method with out argument  reacts on elements of array  as string and sort them in dictionary order (lexicographic ) (that's weird 🙄)
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
const num = () =>{

return 9;
};

console.log(num() < 10); // true
```

num function returns 9 which is less than 10  
***

```js
console.log(4 + (5 - - 4) - - 5)// 18
```

1:(5 - - 4) => 5 +4 => 9
2: 4 + 9 => 13
3: 13 - - 5 => 13 + 5 => 18
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
console.log(1..toString() === "1");// true (that's weird 🙄)
```

why its weird 😵?  
1: floating point 1.0   
2: .toString()   
first . is for floating point 1.0  
***

```js
const value = "123abc";
const result = Number(value);

console.log(typeof result); "number" 
```

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
const arr = [1, 2, 3];
arr[5] = 6;
console.log(arr.length); //6 with two empty spaces
```

***

```js

function display()  
{  
  console.log("10"+(20+30));  // "1050"
    console.log("10"+20+30); // 102030
console.log(10+20+"30") // 3030

}  
display();  
```

why its weird 😵?  
 string concatenation because of +  
***

```js

let a=[]
let b=""
console.log(a==b) // true
```

why its weird 😵?  
loose equal  == converts  one or both values to same type and [] is converted to ""
[] = "" // true
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
a = a + [4] // 1,2,34 both a and [4]converted to string and concat
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

function test(x){
if(x > 0){
test(x-1)
}
console.log(x)// 0 1 2 3 4 5
}
let data = 5
test(data);
```

why its weird 😵?    

***

```js
function fun(a, b, c) {
return b + c
}
fun(5, 3, "wowwwwww", "this is so cool") // '3wowwwwww' string concatenation 
```

```js
setTimeout(()=>{console.log("second")},0)
console.log("first")

```

"first"  
"second"   
set time out  is Asynchronous  
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

let numbers = [1, 2, 3, 4, NaN];
console.log(numbers.indexOf(NaN), typeof numbers[-1] );// -1 'undefined'
```

Javascript is not yet done...... continue... (that's weird 🙄)
