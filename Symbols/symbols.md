# Symbols in ES6

Symbols are new primitive data types in ES6. There are two key points for Symbols:-

* Symbols are unique and Immutable
* Symbols can be used as identifiers for adding properties in an object.

## Creating a Symbol

Creating a symbol is very simple and can be create as like calling a function.
i.e.

```js
let key = Symbol();
```

**Note:**
* A symbol is created with new keyword and calling like a function and if we try to create it using new keyword, it'll throw runtime exception.
* A symbol is unalterable and unique as well.


Creating a Symbol with description.
i.e.

```js
let key1 = Symbol("A secret Key");
let key2 = Symbol("A secret Key");
```

Both Symbols look same but they are unique.


### Using Symbols to create object

1. For creating custom object :-

```js
let email = Symbol();

let user = {
firstName: 'abc',
lastName: 'xyz',
[email]: 'abc.xyz@gmail.com'
}
```

2. For creating Map Object :-

```js
let a = new Map();
{
let key = Symbol();
a.set(key, "A secret key");
console.log(a.get());
}
```