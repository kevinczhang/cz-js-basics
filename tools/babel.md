---
description: Babel is a JavaScript compiler
---

# Babel

{% embed url="https://babeljs.io/docs/en/" %}

Babel is a toolchain that is mainly used to convert ECMAScript 2015+ code into a backwards compatible version of JavaScript in current and older browsers or environments.

* Transform syntax
* Polyfill features that are missing in your target environment \(through [@babel/polyfill](https://babeljs.io/docs/en/babel-polyfill)\)
* Source code transformations \(codemods\)

### Features

#### Babel-Plugins

Plugins and Presets are config details for Babel to transpile the code. Babel supports a number of plugins, which can be used individually, if we know the environment in which the code will execute.

#### Babel-Presets

Babel presets are a set of plugins, i.e., config details to the babel-transpiler that instruct Babel to transpile in a specific mode. We need to use presets, which has the environment in which we want the code to be converted. For example, es2015 preset will convert the code to es5.

#### Babel-Polyfills

There are some features like methods and objects, which cannot be transpiled. At such instances, we can make use of babel-polyfill to facilitate the use of features in any browser. Let us consider the example of promises; for the feature to work in older browsers, we need to use polyfills.

#### Babel-Cli

Babel-cli comes with a bunch of commands where the code can be easily compiled on the command line. It also has features like plugins and presets to be used along with the command making it easy to transpile the code at one go.

### Advantages

* BabelJS provides backward compatibility to all the newly added features to JavaScript and can be used in any browsers.
* BabelJS has the ability to transpile to take the next upcoming version of JavaScript - ES6, ES7, ESNext, etc.
* BabelJS can be used along with gulp, webpack, flow, react, typescript, etc. making it very powerful and can be used with big project making developer’s life easy.
* BabelJS also works along with react JSX syntax and can be compiled in JSX form.
* BabelJS has support for plugins, polyfills, babel-cli that makes it easy to work with big projects.

### Disadvantages

* BabelJS code changes the syntax while transpiling which makes the code difficult to understand when released on production.
* The code transpiled is more in size when compared to the original code.
* Not all ES6/7/8 or the upcoming new features can be transpiled and we have to use polyfill so that it works on older browsers.

