# Template String

Template string also known as Template Literals.Following are the features of Template string :- 

1. Embadding expression in to string
2. Multiline string features
3. String interpolation

Syntax 

`string text`

`string text line 1
 string text line 2`

`string text ${expression} string text`

tag `string text ${expression} string text`

In ES6 there are two literals
1. Template literals ( Template string )
2. Tagged template literals (function calls)


### Multi-line strings
Any new line characters inserted in the source are part of the template literal. Using normal strings, you would have to use the following syntax in order to get multi-line strings:

```js
console.log('string text line 1\n' +
'string text line 2');
// "string text line 1
// string text line 2"
```

To get the same effect with multi-line strings, you can now write:
```js
console.log(`string text line 1
string text line 2`);
// "string text line 1
// string text line 2"
```

### Expression interpolation
In order to embed expressions within normal strings, you would use the following syntax:

```js
let a = 5;
let b = 10;
console.log('Fifteen is ' + (a + b) + ' and\nnot ' + (2 * a + b) + '.');
// "Fifteen is 15 and
// not 20.
```

Now, with template literals, we can substitute values like this:

```js
let a = 5;
let b = 10;
console.log(`Fifteen is ${a + b} and
not ${2 * a + b}.`);
// "Fifteen is 15 and
// not 20.
```


### Tagged template literals
A more advance feature of template literals is **Tagged template litrals**. Tagged are parsed and used with functions. First argument of the function contains array of string values while remaining are related with expression.

```js
const name = 'Bob';
const age = 20;

function myFunction(strings, name, age){
  console.log(strings);
  console.log(name);
  console.log(age);
}

myFunction`${name} is ${age} old boy`;
```
