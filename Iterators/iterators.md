# Iterators

## Iterators in ES6
An object is an iterator when it knows how to access items from a collection one at a time, while keeping track of its current position within that sequence. In JavaScript an iterator is an object that provides a next() method which returns the next item in the sequence. This method returns an object with two properties: done and value.

Once created, an iterator object can be used by successively calling next()

```js
function makeIterator(array){
    let nextIndex = 0;
    return {
    next() {
       const length = array.length;
       return nextIndex < length ?
              {value: array[nextIndex++], done: false} :
              {done: true};
       }
    };
}

let iterator = makeIterator([1,2,3])

console.log(iterator.next())
console.log(iterator.next())
console.log(iterator.next())

```


 ## for...of loop in ES6

 In simple words, Iterators return object with value and done =false if there is next value otherwise no value and done=true means no more value in a collection. In javascript, collections like Array, Map & Set etc, all have 3 default iterators - entries, values & keys.
Es6 introduced a new syntax for dealing with iterables objects that is for...of statement.

 ###Syntax

 for (variable of iterable) {
   statement
 }

```js
const words = ["abc", "xyz", "aaaa"];

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


## Making an object iterable 

By default only those collection which are iterable can be iterated using for...of loop. What about Object? They are not iterable but we can make them iterable too. (PS:- **strings are iterable**)

Let say we have following object and what happens if try to iterate it:- 

```js
const range = {
  from: 1,
  to: 5s
};

for(let num of range) {
 console.log(num);
}
```

It will throw an error as:- 

```js
Uncaught TypeError: range is not iterable
```

So now let's make it iterable too. 


#### Symbol.iterator

We can easily grasp the concept of iterables by making one of our own. For instance, we have an object that is not an array, but looks suitable for for..of like range object above. 

To make the range object iterable *(and thus let `for..of` work)* we need to add a method to the object named **`Symbol.iterator`**. Now let's understand how this works:-  

1. When `for...of` runs, it will call the `Symbol.iterator` function only once which return an object.
2. Now `for...of` will only work with returned object. 
3. Return object must contain function named as ***`next()`***.
4. This `next()` function must return another object of the for of `{done: Boolean, value: any}`, where `done` key will have value as `true/false` depending upon the iteration, so if it's `false` then it `value` key will consist value otherwise `done` is `true` and iteration is finished. 

Here it is implementation:- 

```js
const range = {
  from: 1,
  to: 5,
  [Symbol.iterator]() {
    return {
      current: this.from,
      last: this.to,
       next() {
         if (this.current <= this.last) {
           return { done: false, value: this.current++ };
          } else {
            return { done: true };
          }
      }
    }
  }, 
};
```

now it works!
```js
for (let num of range) {
  console.log(num); // 1, 2, 3, 4, 5
}