 # What is EcmaScript and its major versions releases ?


### History 
ECMAScript (commonly abbreviated to ES) was created to standardize javascript.Over the years, multiple versions have been released, each introducing new features to make code more readable, concise, and easier to maintain. This repository covers the essential features from ES6 to ES13, including explanations, examples, and interactive code samples.


 #### Versions 
 Below is the list of showing all versions of ECMAScript and some major versions introduced in these versions. 

 **Edition**   |     **Published Date**     |     **Changes from prior version**
:-------------:|:--------------------------:|---------------------------------
 1             |         June 1997          |     First edition 
 2             |         August 1998          |     Only Editorial Changes
 3             |         December 1999      |     Added :- <br><ul><li>Regular Expression </li><li>String handling </li><li>new control statement </li><li>try/catch exception handling </li><li>numeric output format handling </li></ul>       
4              |        Abandoned(July 2008)           |    4th Edition was abandon due to political differences due to langauge complexity
5              |         December 2009      |     Added :- <br><ul><li>strict mode </li><li>Clarifies ambugiuties in 3rd edition </li><li>getter/setter</li><li>library support for JSON </li> </ul>                      
5.1            |         June 2011          |     This edition was fully aligned with edition 3
6              |         June 2015          |     Initially named as ECMAScript6(ES6) but renamed ECMAScript 2015.Added new syntax for developing complex applications.<br> Newly added syntax are :- <br><ul><li>class & modules </li><li>const & let </li><li>arrow function</li><li>generators</li><li>collections</li><li>promises etc.</li></ul>It is also known as ES6 Harmony.                                       
7             |          June 2016          |     Known as EcmaScript2016(ES7). It includes the :- <br><ul><li>Array **includes** method</li><li>exponentitation operator(**) etc</li></ul>
8             |          June 2017 |     Known as ECMAScript 2017 (ES8). It includes the :- <br><ul><li>Async/Await</li><li> Object entries</li><li> Object Values</li> <li> string padding</li></ul>
9             |          June 2018 |     Known as ECMAScript 2018 (ES9). It includes the :- <br><ul><li>Async Iteration</li><li>Rest/Spread propertie</li></ul>
10             |          June 2019 |    ECMAScript 2019 (ES10). It includes the :- <br><ul><li>Array flat</li><li>Array flatMap</li> <li>Array flatMap</li> <li>String trimStart</li> <li>String trimEnd</li></ul>
11             |          June 2020 |    ECMAScript 2020 (ES11). It includes the :- <br><ul><li>Optional Chaining</li><li>Nullish Coalescing</li> <li>Dynamic Import</li> <li>BigInt</li> <li>Promise.allSettled</li><li>GlobalThis</li> </ul>
12             |          June 2021 |    ECMAScript 2021 (ES12). It includes the :- <br><ul><li>Private Class Fields</li> <li>Numeric Separators</li> <li>String.prototype.replaceAll</li> <li>WeakRefs</li> <li>FinalizationRegistry</li> </ul>
13             |          June 2022 |    ECMAScript 2022 (ES13). It includes the :- <br><ul><li>Top-level await</li> <li>Private Methods and Accessors</li> <li>Ergonomic brand checks for Private Fields</li></ul>
14             |          June 2023 |    ECMAScript 2023 (ES14). It includes the :- <br><ul><li>Array findFromLast</li> <li>Array findFromLastIndex</li> <li>Import Assertions</li></ul>

### ES6 (2015)

| Feature                         | Description                                                                            | Example                                                                                  |
|---------------------------------|----------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| **Destructuring**               | Unpack values from arrays or properties from objects into distinct variables.           | `const { name, age } = person;`                                                          |
| **Template Literals**           | Multiline strings and embedded expressions.                                            | `` const greeting = `Hello, ${name}!`; ``                                                |
| **Spread Operator**             | Expand iterable elements or arguments.                                                 | `const arr2 = [...arr1, 4, 5, 6];`                                                       |
| **Promises**                    | Handle asynchronous operations.                                                        | `new Promise((resolve, reject) => { ... });`                                             |
| **Modules**                     | Modularize code by exporting and importing.                                            | `import { add } from './utils.js';`                                                      |
| **Generators**                  | Functions that can be paused and resumed.                                              | `function* generator() { yield 'Hello'; yield 'World'; }`                                |
| **Arrow Functions**             | Shorter syntax for writing functions.                                                  | `const add = (a, b) => a + b;`                                                           |
| **Classes**                     | Syntactic sugar over the prototype-based inheritance model.                            | `class Person { constructor(name) { this.name = name; } }`                               |
| **Let and Const**               | Block-scoped variable declarations.                                                    | `let x = 1; const y = 2;`                                                                |
| **Default Parameters**          | Default values for function parameters.                                                | `function add(a, b = 1) { return a + b; }`                                               |
| **Rest Parameters**             | Combine multiple arguments into an array.                                              | `function sum(...args) { return args.reduce((acc, val) => acc + val, 0); }`              |
| **Enhanced Object Literals**    | Shorthand for defining properties and methods in objects.                              | `const obj = { name, greet() { console.log('Hello'); } };`                               |
| **Symbols**                     | Unique and immutable data type used as object keys.                                    | `const sym = Symbol('description');`                                                     |
| **Iterators and For...of Loop** | Iteration protocols for custom and built-in iterables.                                 | `for (const value of array) { console.log(value); }`                                     |
| **Map, Set, WeakMap, WeakSet**  | New collection types for better handling of data.                                      | `const map = new Map();`                                                                 |

### ES7 (2016)

| Feature                         | Description                                                                            | Example                                                                                  |
|---------------------------------|----------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| **Array.prototype.includes**    | Check if an array includes a certain element.                                          | `const hasValue = [1, 2, 3].includes(2);`                                                |
| **Exponentiation Operator**     | Perform exponentiation using a new operator.                                           | `const square = 3 ** 2;`                                                                 |

### ES8 (2017)

| Feature                         | Description                                                                            | Example                                                                                  |
|---------------------------------|----------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| **Async/Await**                 | Cleaner promise-based asynchronous code.                                               | `async function fetchData() { ... }`                                                     |
| **Object.entries**              | Return an array of key-value pairs from an object.                                     | `const entries = Object.entries(obj);`                                                   |
| **Object.values**               | Return an array of values from an object.                                              | `const values = Object.values(obj);`                                                     |
| **String padding**              | Pad the beginning or end of a string.                                                  | `const str = '5'.padStart(2, '0');`                                                      |
| **Trailing commas in functions**| Allow trailing commas in function parameter lists and calls.                           | `function foo(a, b, c,) { ... }`                                                         |

### ES9 (2018)

| Feature                         | Description                                                                            | Example                                                                                  |
|---------------------------------|----------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| **Async Iteration**             | Asynchronous iteration protocols.                                                      | `for await (const value of asyncIterable) { ... }`                                       |
| **Promise.prototype.finally**   | Add a final block to a promise chain.                                                  | `promise.finally(() => { ... });`                                                        |
| **Rest/Spread properties**      | Rest properties collect remaining properties, Spread properties spread an object.      | `const { a, ...rest } = obj; const newObj = { ...obj };`                                 |
| **RegExp Lookbehind Assertions**| Allow regex to match preceding characters.                                             | `/(?<=\$)\d+/`                                                                           |

### ES10 (2019)

| Feature                         | Description                                                                            | Example                                                                                  |
|---------------------------------|----------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| **Array.prototype.flat**        | Flatten nested arrays.                                                                 | `const arr = [1, [2, [3]]].flat(2);`                                                     |
| **Array.prototype.flatMap**     | Map and flatten arrays in one step.                                                    | `const arr = [1, 2, 3].flatMap(x => [x, x * 2]);`                                        |
| **Object.fromEntries**          | Transform a list of key-value pairs into an object.                                    | `const obj = Object.fromEntries([['a', 1], ['b', 2]]);`                                  |
| **String.prototype.trimStart**  | Trim whitespace from the beginning of a string.                                        | `const str = '  hello'.trimStart();`                                                     |
| **String.prototype.trimEnd**    | Trim whitespace from the end of a string.                                              | `const str = 'hello  '.trimEnd();`                                                       |
| **Optional catch binding**      | Omit the catch binding parameter if not needed.                                        | `try { ... } catch { ... }`                                                              |

### ES11 (2020)

| Feature                         | Description                                                                            | Example                                                                                  |
|---------------------------------|----------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| **Optional Chaining**           | Access deeply nested properties without checking each reference.                      | `const value = obj?.prop?.subProp;`                                                      |
| **Nullish Coalescing**          | Provide a default value when dealing with null or undefined.                           | `const value = foo ?? 'default';`                                                        |
| **Dynamic Import**              | Import modules dynamically at runtime.                                                 | `const module = await import('./module.js');`                                            |
| **BigInt**                      | Represent integers with arbitrary precision.                                           | `const bigInt = 1234567890123456789012345678901234567890n;`                              |
| **Promise.allSettled**          | Wait for all promises to settle (either resolved or rejected).                         | `const results = await Promise.allSettled([promise1, promise2]);`                        |
| **GlobalThis**                  | Standardized access to the global this context.                                        | `globalThis.setTimeout(() => { ... }, 1000);`                                            |
| **MatchAll**                    | Return an iterator for all matched groups.                                             | `const matches = str.matchAll(/regex/g);`                                                |

### ES12 (2021)

| Feature                         | Description                                                                            | Example                                                                                  |
|---------------------------------|----------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| **Private Class Fields**        | Define private fields in classes.                                                      | `class MyClass { #privateField; }`                                                       |
| **Logical Assignment Operators**| Perform logical operations and assign the result in one step.                          | `x ||= y;`                                                                               |
| **Numeric Separators**          | Improve readability of numeric literals.                                               | `const largeNumber = 1_000_000;`                                                         |
| **String.prototype.replaceAll** | Replace all occurrences of a substring in a string.                                    | `const newStr = str.replaceAll('foo', 'bar');`                                           |
| **WeakRefs**                    | Create weak references to objects.                                                     | `const weakRef = new WeakRef(obj);`                                                      |
| **FinalizationRegistry**        | Manage cleanup of resources.                                                           | `const registry = new FinalizationRegistry((value) => { ... });`                         |

### ES13 (2022)

| Feature                         | Description                                                                            | Example                                                                                  |
|---------------------------------|----------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| **Top-level await**             | Use await at the top level in modules.                                                 | `const data = await fetchData();`                                                        |
| **Private Methods and Accessors**| Define private methods and accessors in classes.                                      | `class MyClass { #myPrivateMethod() { ... } }`                                           |
| **Ergonomic brand checks for Private Fields** | Simplify checks for private fields in classes.                      | `class MyClass { #privateField; hasPrivateField(obj) { return #privateField in obj; } }` |

### ES14 (2023)

| Feature                         | Description                                                                            | Example                                                                                  |
|---------------------------------|----------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| **Array findFromLast**          | Find last occurrence in arrays.                                                        | `arr.findLast(element => element > 5)`                                                   |
| **Array findFromLastIndex**     | Find last occurrence index in arrays.                                                  | `arr.findLastIndex(element => element > 5)`                                              |
| **Hashbang Grammar**            | Use #! for shell scripting.                                                            | `#!/usr/bin/env node`                                                                    |
| **Import Assertions**           | Specify module type for imports.   

