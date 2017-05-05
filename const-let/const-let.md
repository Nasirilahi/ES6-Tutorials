# Variables in ES6

Variables are used to store values, act as container for values. Variables must be declare before used. Earlier variables are declared used **var** keyword so declare a variable in javascript as :

```js
var variable_name;
```

After declaring we can assign values to these variables as: 

```js
variable_name =10   
```
or it can be assign at the time of declaration.
In ES6 we can declare variable using **let** and **const**. So before going to these two we need to understand **var** properly.

## The var keyword 
1. **var** variables can be udpated and redefined. e.g. 
```js
var width = 100;
console.log(width); // 100
width = 200;
console.log(width); // 200
```
so we can update variable and it is not a big deal but if we put var before width in line 22 then it will work and won't yell on us because variables can be redefined or updated.

2. **var** variables were function scode not block scope.
**Scoping** means where variables are available in the code. So if a variable is declared inside a function then it will be available in to the whole function  even in nested function.

```js
const myFunction = () => {
   var a=0;
  for(var i=0;i< 5;i++){
    a++;
    console.log('a',a);
  };
  console.log(i);
};

myFunction();
```
It will print the **i** value as 5 because it has been declared once and will be available to the whole function.

```js
function setWidth() {
  var width = 100;
  console.log(width);
}
setWidth();
console.log(width);
```
**width** will be undefined here because its scoped inside the function only and it is local to setWidth function but will be available in to the whole function. But if we put this outside the setWidth function then it will be available to whole window.

Let understand one more problem of function scoping.
I want to do something on condition matching like i have age variable and if this age variable is greater than 10 then want to create another variable.
```js
if(age > 120) {
  var years = age * 7;
  console.log("You are "+years+" dog years old!");
}
```
however **years** is a temporary variable and is being used only in if statement so if this code statement is in function then it will be in that function scope otherwise it will be in global scope and it is getting leak outside the if statement so **let** and const will be usefull.

### block scope 
So whenever we find any starting **{** and a closing **}** its a block. It can be with be a function, loop statment or conditional statement. 

```js
// variables declared here will be in global scope.
function myFunction(){
// variables declared here will be in function block scope.

if(){
// scope only in if statement and will be undefined outside this if statement.
}
}
```
## let and const 
In ES6 we can declared variables using **let** and **const** variables declared using these will be in block scope not like function as with **var** variables.

```js
var age = 100;
if(age > 12) {
  let dogYears = age * 7;
  console.log(`You are ${dogYears} dog years old!`);
}
console.log(dogYears); // error because it's scoped only to the above block
```
So now we need to remember that ** We can declare variables only in its scope.**
lets we have declared the following variables :- 
```js
let a = 10; 
let b = 20;
const c = 30;
```
and if we try to **update or re-declare any of this variable we will get error**
```js
let a = 30 // error here **duplication declaration**
```
again working back setWidth function and declaring variables using let/const in that 
```js
function setWidth() {
  let width = 100;
   if(width === 100){
      let height = width * 2;
      console.log('width',width);     // both variable will be available here 
      console.log('height', height);
   }
   console.log('width',width);
   console.log('height', height); // height will be undefined here because its scoped only in if statement.
}
setWidth();
```
#### const keyword 
const keyword has the same block scope as let keyword but there difference is:- 
**const variable can not be updated.**
const variables are *read only*.
```js
const myVar = 10;
myVar = 30;  //myVar is read-only
```
