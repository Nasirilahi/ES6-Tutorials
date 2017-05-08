# Destructing 

## Destructing = Unpacking values from Arrays or properties from objects

Destructing is a way of getting values stored in to objects and arrays (possibly in nested way).

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

Both these same patterns can be use to extract data from this object but extracting multiple properties at the same time was introduced in ES6.

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
