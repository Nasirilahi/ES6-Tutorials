# Spread Operator
Spread operator is used for the expression where :- 
1. Multiple arguments for function calls. Syntax -------> myFunction(...iterableObj);
2. Multiple elements for Array literal.  Syntax -------> [...iterableObj, 4, 5, 6];
3. Multiple variables for destructing assignment.  Syntax -------> [a,b ...rest] = [1,2,3,4,5,6,7,8,9]

## When we want to use an array as arguments in a function then we use the javascript **apply** method

```js
function myFunction(x, y, z) { 
console.log(x);
console.log(y);
console.log(z);
}
const args = [0, 1, 2];
myFunction.apply(null, args);
```

With spread syntax the above can be written as:

```js
function myFunction(x, y, z) { }
let args = [0, 1, 2];
myFunction(...args);
```

Any argument in the argument list can use spread syntax and it can be used multiple times.

```js
function myFunction(v, w, x, y, z) { }
let args = [0, 1];
myFunction(-1, ...args, 2, ...[3]);
```

## Spread operator with array literal
Spread operator is used for new array construction from an existing array. Without spread operator creating new array will be complicated and have to use push, slice functions, But with spread operator it will be very easy.


```js
let cold = ['autumn', 'winter'];  
let warm = ['spring', 'summer']; 
let weather = [...cold, ...warm ];
console.log(weather);
```


**Note:** :Just like spread for argument lists, ... can be used anywhere in the array literal and it can be used multiple times.