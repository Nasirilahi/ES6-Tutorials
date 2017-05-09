# Modules 

In modules systems we have only two points to discuss:- 
* export 
* import

## export

In CommonJS, you export values by exposing them on module.exports. As seen in the snippet below, we can expose anything from a value type to an object, an array, or a function.

```js
module.exports = 1
module.exports = NaN
module.exports = 'foo'
module.exports = { foo: 'bar' }
module.exports = ['foo', 'bar']
module.exports = function foo () {}
```

Declaration in ES6 modules are scoped to that modules only. Variables/methods declared within that module is not accessible other module untill those are imported.
In ES6 we can also expose 
```js
export const foo = 'bar'
export let baz = 'ponyfoo'
```

### exporting a default binding
We can expose default by changing module.exports in to export default

```js
export default 'foo';
```

**Note:** We can expose only one thing as default at a time but there can be multiple export.

### Export Lists

```js
var foo = 'ponyfoo'
var bar = 'baz'
export { foo, bar }
```


## Import 
These statements are the counterpart of export, and they can be used to load a module from another one – first and foremost.It is same as **require** function in ES5.

### Import default exports 

```js
import _ form 'lodash';
``` 

### Importing the named exports
These are imported same as default but within the curly braces.

```js
import { map, reduce } from 'lodash';
```

Renaming 
```js
import {map as lodashMap} from 'lodash';
import {map as googleMap} from 'google-map';
```


### Importing all the modules 
```js
import * as _ from 'lodash';
_.reduce(arrVar);
```

