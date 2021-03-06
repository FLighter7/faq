## What is it and difference between IIFE, CJS, AMD, UMD, ESM, SystemJS?

#### What is it?

They are module formats. They say how to connect our js-files through the specific wrappers or operators.

#### Short descriptions

- **IIFE** - *Immediately Invoked Function Expression* - All dependencies are involved into a named (or unnamed) self-executing function that returns an object (our module). Example:
```js
// Module name in a global scope
const ourModuleName = (() => {
  // Any code here
  return {
    getFoo: () => 'foo',
  }
})();
```

- **CJS** - *CommonJS*, *ServerJS* (old) - A module format commonly used in Node.js and other ecosystems outside of the browser. Keys are: `module.exports` or `exports` - to export a module, `require` - to import a module. <br>- Because of `require` is just a function, we can use dynamic imports. <br>- Pure CJS modules cannot be used in the browser and need transpilation. Example:
```js
// Import some modules
const someModule1 = require('module-name-1');
const someModule2 = require('./path-to-module.js');

// Do something
const foo = someModule1.getSomething();
const bar = () => someModule2.doSomething();

// Export module
exports.foo = foo;
exports.bar = bar;
// Or (equivalently)
module.exports = {
  foo,
  bar,
}
```

- **AMD** - *Asynchronous Module Definition* - A module format used in RequireJS library and it's more suitable for the browser instead of CJS format. The main idea is that RequireJS is an implementation of AMD, while at the same time trying to keep the spirit of CJS. Keys are: `define` - to define a module, `require` - to use a module. Example:
```js
// Define some module
define('someModuleName', () => {
  // Any code here
  return {
    getFoo: () => 'foo',
  }
});

// Use the defined module
require(['someModuleName'], someModuleName => {
  someModuleName.getFoo();
});
```

- **UMD** - *UmdJS*, *Universal Module Definition* - UMD is designed to work everywhere - on the server side and the browser side. It supports AMD, CJS and IIFE formats and often used as a result of bundler transpilation.
```js
// Define a module system
(function(global, factory) {
  typeof exports === 'object' && typeof module !== 'undefined'
    ? module.exports = factory()
    : typeof define === 'function' && define.amd
      ? define(factory)
      : (global = typeof globalThis !== 'undefined' ? globalThis : global || self, global.A1 = factory());
}(this, (function() {
  // Code of the module is here
  return {
    getFoo: () => 'foo',
  }
})));
```

- **ESM** - *ES Modules*, *ES2015 Modules*, *ES6 Modules*, etc. - Since 2015 it is the native format of the js module system. Keys are: `import` - to import a module, `export` - to export a module. Works in modern browsers, tree-shakeable (instead of all of the above), asynchronous. Example:
```js
// Import some modules
import someModule1 from 'module-name-1';
import someModule2 from './path-to-module.js';

// Do something
const foo = someModule1.getSomething();
const bar = () => someModule2.doSomething();

// Export module
export default {
  foo,
  bar,
}
```

- **SystemJS** - *System Module* - SystemJS is a universal module loader that supports CJS, AMD, and ESM modules to run them in old browsers. Keyword is `System.register` - to register a module. Requires SystemJS package installed. Example:
```js
System.register([], function(exports) {
  return {
    execute: function () {
      // Code of the module is here
      exports('getFoo', getFoo);
      const getFoo = () => 'foo';
    }
  };
});
```

### Links

- [Understanding JavaScript module formats and tools](https://weblogs.asp.net/dixin/understanding-all-javascript-module-formats-and-tools#webpack-module-bundle-from-cjs-amd-es-modules)
- [What are CJS, AMD, UMD, ESM, System, and IIFE?](https://betterprogramming.pub/what-are-cjs-amd-umd-esm-system-and-iife-3633a112db62)
- [What are CJS, AMD, UMD, and ESM in Javascript?](https://irian.to/blogs/what-are-cjs-amd-umd-and-esm-in-javascript/)
- [Relation between CommonJS, AMD and RequireJS?](https://stackoverflow.com/questions/16521471/relation-between-commonjs-amd-and-requirejs)
