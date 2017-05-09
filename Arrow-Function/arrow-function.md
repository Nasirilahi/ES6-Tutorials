#Arrow Function in ES6

Arrow function is shorter notation for regular functions. This does not bind its own **this, arguments** and **super**.

### Basic syntax 
(par1, par2, par3, ..., parN) => { statements}
(par1, par2, par3, ..., parN) => expression  

it is equivalent to :  (param1, param2, …, paramN) => { return expression; }

**Note:** Some key points :- 
1. Parantheses are optional if there is only one parameter.Below both lines are equal :- 

    (par1) => { statements }  //or
    par1 => { statements }

2. Paranthesize the body to return an object literal.
3. Rest parameters and default values are supported by these functions.
4. Destructing is supported on parameters list.

The following variables are all lexical inside arrow functions:
    * arguments
    * super
    * this
    * new.target

Two factors were the reason of introducing **arrow function** : 
1. Shorter syntax
2. non-binding of **this**

1. Shorter syntax

Regular function 
```js
let greeting = function(message, name){
    return message + ' ' + name;
}

console.log(greeting('hello', 'Bob'));
```

Arrow function 
```js
const greeting = (message, name) => {
    return message + ' ' + name;
}

console.log(greeting('hello', 'Bob'));
```

## Shorter form of the function 

```js
let materials = [
  'Hydrogen',
  'Helium',
  'Lithium',
  'Beryllium'
];

let materialsLength1 = materials.map(function(material) { 
  return material.length; 
}); // [8,6,7,9]

let materialsLength2 = materials.map((material) => {
  return material.length;
}); // [8,6,7,9]

let materialsLength3 = materials.map(material => material.length); // [8,6,7,9]
```

## No binding of **this**
Every tradional function defined its own **this**. So this will prevent us of passing the this inside a surronding function calling from a callback function.i.e

```js
function Person() {
  // The Person() constructor defines `this` as an instance of itself.
  this.age = 0;

  setInterval(function growUp() {
    // In non-strict mode, the growUp() function defines `this` 
    // as the global object, which is different from the `this`
    // defined by the Person() constructor.
    this.age++;
  }, 1000);
}

var p = new Person();
```

In ES3/5 it can be fix by assigning this to a var variable and then this will be accessible inside the surrounding function.

```js
function Person() {
  this.age = 0;
  var self = this;
  setInterval(function growUp() {
      //self is scoped now in outer function scope
    self.age++;
  }, 1000);
}
```

In ES6 this can be achieved in two ways:- 
1. By binding this to surrounding function where we need to access this.
2. By arrow function


1. bind(this)

```js
function Person() {
  this.age = 0;
  setInterval(function growUp() {
    this.age++;
  }, 1000).bind(this);
}
```

2. arrow function 

```js
function Person() {
  this.age = 0;
  setInterval(growUp = ()=> {
      //Arrow function will do auto binding
    this.age++;
  }, 1000);
}
```

#### Following are the points where arrow function will not work

Use of the new operator

Arrow functions cannot be used as constructors and will throw an error when used with new.

```js
var Foo = () => {};
var foo = new Foo(); // TypeError: Foo is not a constructor
```

Use of prototype property

Arrow functions do not have a prototype property.

```js
var Foo = () => {};
console.log(Foo.prototype); // undefined
```

Line breaksEDIT
An arrow function cannot contain a line break between its parameters and its arrow.

```js
var func = ()
           => 1; 
// SyntaxError: expected expression, got '=>'
```