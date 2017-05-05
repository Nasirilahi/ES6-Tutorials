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
```
var width = 100;
console.log(width); // 100
width = 200;
console.log(width); // 200
```
so we can update variable and it is not a big deal but if we put var before width in line 22 then it will work and won't yell on us because variables can be redefined or updated.

2. **var** variables were function scode not block scope.
**Scoping** means where variables are available in the code. So if a variable is declared inside a function then it will be available in to the whole function  even in nested function.

```
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

```
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
```
if(age > 120) {
  var years = age * 7;
  console.log("You are "+years+" dog years old!");
}
```
however **years** is a temporary variable and is being used only in if statement so if this code statement is in function then it will be in that function scope otherwise it will be in global scope and it is getting leak outside the if statement so **let** and const will be usefull.

