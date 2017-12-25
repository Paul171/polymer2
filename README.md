# Start with Polymer3.0

## install components from yarn
1. `yarn init`:set up your project
2. update `package.json` by adding `"flat": true`
3. install `@polymer/polymer@next` for polymer 3 and install the polyfills from `@webcomponents/webcomponentsjs`

** solve the version conflicts by flat **

 * Explicitly install web components with `--flat` and Leave the `"flat": true` out of the package.json file 

> yarn add --flat @polymer/polymer@next


* Use separate directories.
    * set up the `package.json` file in the project directory with `"flat": true` and add a subdirectory with its own `package.json` for packages that need nested dependencies.

** Import dependencies **

* import a module in HTML using `<script type="module">`
* inside a module, you can import a module using the `import` statement
* few important things to note about modules and the import statemen
    * Like HTML imports, the import must use a path, not a module name.
    * The imported path must start with "./", "../", or "/".
    * The import statement can only be used inside a module (that is, an external file or inline script loaded with `<script type="module">`.
    * Modules always run in strict mode.
* register an element but don't export any symbols 
    * `import "../@polymer/paper-button/paper-button.js"`
* For behaviors, you'll typically import the behavior explicitly
    * `import {IronResizableBehavior}
    from "../@polymer/iron-resizable-behavior/iron-resizable-behavior.js"`
* For utility modules like Async that export several members, you can import individual members, or import the entire module
    * `import * as Async from "../@polymer/polymer/lib/utils/async.js"
    Async.microTask.run(callback);`
** Dynamic import **
* using the `import()` and return `Promise`
```javascript
import('my-view1.js').then((MyView1) => {
  console.log("MyView1 loaded");
}).catch((reason) => {
  console.log("MyView1 failed to load", reason);
});
```

** Defining elements **
* Imports use ES6 import syntax, not `<link rel="import">`
* Templates are defined by providing a template getter that returns a string—not the `<dom-module>` and `<template>` elements.
* Instead of defining globals (for example, when defining behaviors or mixins) use the export statement to export symbols from modules


* `Polymer.importHref` is no longer supportted
* For reusable element, the import for the Polymer `Element` class would omit the `node_modules` folder

```javascript
import {Element as PolymerElement}
    from '../@polymer/polymer/polymer-element.js';
```
** Previewing projects **
```javascript
polymer serve --npm
polymer test --npm
```

** Upgrading an existing project **
Polymer Modulizer tool in a very early state, can try the Modulizer in [README][https://github.com/Polymer/polymer-modulizer/blob/master/README.md] or join the chat #modulizer on Slack
