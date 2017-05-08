# Destructing 

## Destructing = Unpacking values from Arrays or properties from objects

Destructing is a way of getting values stored in to objects and arrays (possibly in nested way).Same 

### constructing vs Destructing 

Let's first understand how objects can be constructed in javascript :-

There are two ways of constructing an object:- 

1. Declaring an empty object and then defining one property at a time. i.e.  

```js
const myObj = {};
myObject.value1 = 1;
myObject.value2 = 2;
``` 

2. Defining multiple properties at same time an object is being decalred. i.e 

```js
const myObj = { value1:1, value2: 2 };
```

Both these same patterns can be use to extract data from this object and on the left hand side we decide what are to be unpack. 
It was introduced in ES6.This capability is similar to features present in languages such as Perl and Python.

1. Extracting values from the object one at a time :- 

```js
const value1  = myObj.value1;
const value2 = myObj.value2;
```


2. Extracting multiple values at the same time in ES6 code:- 

```js
const { value1, value2 } = myObj;
```

we can also map aliases for the properties according to our choice and this can be very helpful when we have to extract properties with the same name from different objects.

```js
const { value1: myValue1, value2: myValue2 } = myObj;
```

##### Assignment wihout declaration
In previous example we are declaring and assigning the values with extraction, but variables can be declared before and assigned later with extraction.


```js
let a, b;
const myObj = { a:10, b:20 };
({ a, b } = myObj);    //values assignment with extraction 

{ a, b } = myObj; //it will give error;
```

**warning** Make sure a property do exist while extracting that particular property from the object otherwise it will be undefined.

```js
let {foo} = {bar: 'baz'}
console.log(foo)        //undefined
```

#### Default values 
In assignment with destructing we can also give default values to variables, assigning default values may help when we try to pull from the object a non-exist or undefined propty.

```js
let {a = 10, b = 5} = {a: 3};

console.log(a); // 3
console.log(b); // 5
```
In the example above we are extracting only **'a'** property. So initially a has value 10 but after destructing it will have extracted value from the object that is 3.Below code snippet do the same thing :- 


```js
const myObj = { a:3 };
let a = myObj.a === 'undefined' ? 10 :  myObj.a;
```


## Array destructing 

### Basic variables assignment extracted from an array:- 

```js
const foo = ['one', 'two', 'three'];

let [one, two, three] = foo;
console.log(one); // "one"
console.log(two); // "two"
console.log(three); // "three"
```

### Elision

If we want to ignore some values from an array then we can do:- 

```js
const foo = ['one', 'two', 'three', 'four', 'five'];

let [one, two, three,,five] = foo;     //or
// let [,,three] = foo;      //or
// let [,two,,,five] = foo;
console.log(one); // "one"
console.log(two); // "two"
```
### Default values

A variable can be assigned a default, in the case that the value pulled from the array is undefined.(same as in object)

```js
let a, b;

[a=5, b=7] = [1];
console.log(a); // 1
console.log(b); // 7
```

### Swapping without destructing 

```js
let a = 10, b = 20, c;
c = b;
b = a; 
a = c ;
```

But we can do this swaping only in a single line as :- 

```js
let a = 10, b = 20;
console.log('a', a, 'b', b);
[a, b] = [ b,a ];
console.log('a', a, 'b', b);
```

### Returning multiple values from a function 

```js
function myFunction(){
    return [1,2,3,4,5];
}

let [one, two, three, four, five] =  myFunction();
console.log(one);   //1
console.log(two);   //2
console.log(three); //3
console.log(four);  //4
console.log(five);  //5
```
**We can also ignore some values when assigning these to variables**
```js
function myFunction(){
    return [1,2,3,4,5];
}
 
let [one, , three, , five] =  myFunction();
console.log(one);   //1
console.log(three); //3
console.log(five);  //5
```

### Rest operator during array extraction 
When destructing an array we can assign values from starting to some variables and remaining last can be assign to a single variable using **rest operator**

```js
let [one,two, three, ...rest ] = [1,2,3,4,5,6,7,8,9];
console.log(one);       //1
console.log(two);       //2
console.log(three);     //3
console.log(rest);      //[4,5,6,7,8,9]
```

