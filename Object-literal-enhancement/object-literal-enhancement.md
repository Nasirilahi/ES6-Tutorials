# Object Literals Enhancement

There are many new features available when declaring object literals 
1. Shorthand syntax for initializing properties
2. Defining function 
3. Computed property key

## 1. Shorthane syntax for initializing properties
When we want to assign a variable having same name as property then we can give this variable directly by skipping property value.

```js
let foo = 'foo';
let bar = {
    foo     //same as foo:foo
};
console.log(bar.foo);
```

Another Example

```js
var ms = {}

function getItem (key) {
  // write your code here
}

function setItem (key, value) {
   //write your code here
}

function clear () {
  ms = {}
}

module.exports = {
  getItem: getItem,
  setItem: setItem,
  clear: clear
}
```

As in property name is matching with the property value so we can omit these property values and the module.exports object will become :- 

```js
module.exports = { getItem, setItem, clear };
```

## 2. Defining function in ES6 

In ES3/ES5 functions were defined as :- 

```js
let myObj = {
    myFunction: function(){
        console.log('function in ES3/ES5');
    }
};
myObj.myFunction();
```

But in ES6 functions can be defined pretty similiar to property shorthand way:- 

```js
let myObj = {
    myFun(){
        console.log('function in ES6');
    }
};
 myObj.myFun();
```

## 3. Computed property key

With object literals in ES5, we can either have a string literal or a fixed alphanumeric name. ES6 now allows property keys of object literals to be use expressions, making them computed property keys.

```js
var foo = 'bar'
var baz = {}
baz[`foo${foo}`] = 'ponyfoo';
console.log(baz)    // <- { foobar: 'ponyfoo' }
```


One limitation of computed property names is that you won’t be able to use the shorthand expression with it. 

```js
var foo = 'bar'
var bar = 'ponyfoo'
var baz = { [foo] }
console.log(baz);
```