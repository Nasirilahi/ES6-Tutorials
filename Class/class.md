# Classes in Javascript
JavaScript is a prototype-based programming language. Prototype-based is a style of **object-oriented programming** in which reusablity is performed using existing objects instead of a class.

### Classical Inheritance 
In classical inheritance a class is written and then objects are created from that class. So code is on one place and this describes several objects. Now for reusablity code, classes can be organized into hierarchy. More general code is written in a higher level class from which other lower level classs will be inherited.

### Prototype Inheritance 
In the prototypal inheritance form, objects inherit directly from other objects. All of the business about classes goes away. If you want an object, you just write an object. But code reuse is still a valuable thing, so objects are allowed to be linked together in a hierarchy. In javascript, every object has a secret link to the object which created it, forming a chain. When an object is asked for a property that it does not have, its parent object will be asked... continually up the chain until the property is found or until the root object is reached.

## If JavaScript is a prototype-based language, so what are classes in ES6 ?