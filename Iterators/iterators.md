# Iterators

## Iterators in ES6
An object is an iterator when it knows how to access items from a collection one at a time, while keeping track of its current position within that sequence. In JavaScript an iterator is an object that provides a next() method which returns the next item in the sequence. This method returns an object with two properties: done and value.

Once created, an iterator object can be used by successively calling next()

```js
function makeIterator(array){
    var nextIndex = 0;
    return {
    next: function() {
       return nextIndex < array.length ?
              {value: array[nextIndex++], done: false} :
              {done: true};
       }
    };
}

let Iterator = makeIterator([1,2,3])

console.log(Iterator.next())
console.log(Iterator.next())
console.log(Iterator.next())

```


 ## for...of loop in ES6

 In simple words, Iterators return object with value and done =false if there is next value otherwise no value and done=true means no more value in a collection. In javascript, collections like Array, Map & Set etc, all have 3 default iterators - entries, values & keys.
Es6 introduced a new syntax for dealing with iterables objects that is for...of statement.

 ###Syntax

 for (variable of iterable) {
   statement
 }

```js
var words = ["abc", "xyz", "aaaa"];

for(let word of words.entries()){
console.log(word)
}

for(let word of words.values()){
console.log(word)
}

for(let word of words.keys()){
console.log(word)
}

```