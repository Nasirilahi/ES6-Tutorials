# Iterators

## Iterators in ES6
An object is an iterator when it knows how to access items from a collection one at a time, while keeping track of its current position within that sequence. In JavaScript an iterator is an object that provides a next() method which returns the next item in the sequence. This method returns an object with two properties: done and value.

Once created, an iterator object can be used by repeatedly calling next()

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
console.log(Iterator.next())
console.log(Iterator.next())

```

