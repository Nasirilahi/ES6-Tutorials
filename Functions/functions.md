# Parameters handling in functions using ES6

## Parameters in functions
Now in ES6 we can give default values, rest arguments and Destructing to arguments in functions.

1. Default values
2. Rest parameters 
3. Named and Optional parameters

1. Default parameters
Default parameters are used to initialized default value for the parameter if caller does not provide value for the parameter. 
So if parameter is assigned a default value then it will be used in the function if no value or undefined is passed.

Default paramters handling without ES6 

```js
function multiply(a, b) {
  b = (typeof b !== 'undefined') ?  b : 1;
  return a * b;
}

multiply(5, 2); // 10
multiply(5, 1); // 5
multiply(5);    // 5
```

Default paramters handling with ES6

```js
function multiply(a, b = 1) {
  return a * b;
}

multiply(5, 2); // 10
multiply(5, 1); // 5
multiply(5);    // 5
```


2. Rest parameter 
If the last named argument of a function is prefixed with ..., it becomes an array whose elements from 0 to theArgs.length are supplied by the actual arguments passed to the function.


```js
function(a, b, ...theArgs) {
  // ...
}
```

In the above example, theArgs would collect the third argument of the function (because the first one is mapped to a, and the second to b) and all the consecutive arguments.

Difference between rest parameters and the arguments object

There are three main differences between rest parameters and the arguments object:

* rest parameters can contains only the arguments we want to put in this, while the arguments object contains all arguments passed to the function.
* arguments is a object not a real array, while rest parameters are Array instances, meaning methods like sort, map, forEach or pop can be applied on it directly.

### From arguments to an array

```js
// Before rest parameters, the following could be found:
function f(a, b) {
  var args = Array.prototype.slice.call(arguments, f.length);

  // …
}

// to be equivalent of

function f(a, b, ...args) {
  
}
```


3. Named and Optional parameters

How we do default value assignment during destructing :- 

```js
let { x=10, y=20, z= 30 } = { x:1, y:2 };
console.log(x,y,z)  //1, 2, 30
```

So when we pass arguments in a function call, that function first will assign values to those arguements before executing.Since this is an assignment statement so destructing can also be applied here.

* Simple destructing in function arguments

```js
function myFunction({x,y,z}){
    console.log(x,y,z);
}

myFunction({x:10, y:20, z:30});
```

* Destructing with renaming arguments 

```js
function myFunction({x:newX, y:newY ,z:newZ }){
    console.log(newX,newY,newZ);
}

myFunction({x:10, y:20, z:30});
```

* Destructing with default values 

```js
function myFunction({ x=1, y=2, z=3 }){
    console.log(x,y,z);
}

myFunction({x:10, y:20 });
```

* Destructing with default values as individual or as a whole object 

```js
function myFunc({x = 5,y = 8,z = 13} = {x:1,y:2,z:3}) {
	console.log(x,y,z);
};

myFunc(); //1 2 3  (hits the object literal default)
myFunc({}); //5 8 13   (hits the value defaults)
myFunc({x:20})  //20 8 13
```


## Setter/Getter in Javascript

Sometimes we want a value that is based on some other values. For example a fullName can be concatenated using firstName and lastName.
If we have a person object and we want to set firstName, lastName and fullName of that object than we can build functions for this.

```js
let person = {
    firstName: '',
    lastName: '',
    setFirstName:function(firstName){
        this.firstName = firstName;
    },
    setLastName:function(lastName){
        this.setName = lastName;
    },
    getFullName:function(){
        return this.firstName + ' ' + this.lastName;
    }
};

person.setFirstName('abc');
person.setLastName('xyz');
person.getFullName();   // 'abc xyz'
```

This shows that properties of the objects are related. We have a better way of doing this using **setter/getter**.

let's write the above code using set and get function 

```js
let person = {
  firstName :'abc',
  lastName: 'xyz', 
  get fullName(){
    return this.firstName + ' ' +this.lastName;
  },
  set fullName(name){
    let words = name.toString().split(' ');
    this.firstName = words[0] || '';
    this.lastName = words[1] || '';
  }
}


person.fullName = 'Daffodil Software';
console.log(person.fullName);
console.log(person.firstName);
console.log(person.lastName);
```