---
description: >-
  At its core, webpack is a static module bundler for modern JavaScript
  applications.
---

# Webpack

When webpack processes your application, it internally builds a dependency graph which maps every module your project needs and generates one or more _bundles_.

## Entry

An **entry point** indicates which module webpack should use to begin building out its internal dependency graph. webpack will figure out which other modules and libraries that entry point depends on \(directly and indirectly\).

By default its value is `./src/index.js`, but you can specify a different \(or multiple entry points\) by setting an `entry` property in the webpack configuration. 

```javascript
module.exports = {
  entry: './path/to/my/entry/file.js'
};
```

## Output

 The `output` property tells webpack where to emit the bundles it creates and how to name these files. It defaults to `./dist/main.js` for the main output file and to the `./dist` folder for any other generated file.

```javascript
const path = require('path');

module.exports = {
  entry: './path/to/my/entry/file.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'my-first-webpack.bundle.js'
  }
};
```

## Loaders

Out of the box, webpack only understands JavaScript and JSON files. Loaders allow webpack to process other types of files and convert them into valid modules that can be consumed by your application and added to the dependency graph.

At a high level, **loaders** have two properties in your webpack configuration:

1. The `test` property identifies which file or files should be transformed.
2. The `use` property indicates which loader should be used to do the transforming.

```javascript
const path = require('path');

module.exports = {
  output: {
    filename: 'my-first-webpack.bundle.js'
  },
  module: {
    rules: [
      { test: /\.txt$/, use: 'raw-loader' }
    ]
  }
};
```

## Plugins

While loaders are used to transform certain types of modules, _**plugins**_ ****can be leveraged to perform a wider range of tasks like bundle optimization, asset management and injection of environment variables.

```javascript
const HtmlWebpackPlugin = require('html-webpack-plugin'); //installed via npm
const webpack = require('webpack'); //to access built-in plugins

module.exports = {
  module: {
    rules: [
      { test: /\.txt$/, use: 'raw-loader' }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({template: './src/index.html'})
  ]
};
```

In the example above, the `html-webpack-plugin` generates an HTML file for your application by injecting automatically all your generated bundles.

## Mode

 By setting the `mode` parameter to either `development`, `production` or `none`, you can enable webpack's built-in optimizations that correspond to each environment. The default value is `production`.

```javascript
module.exports = {
  mode: 'production'
};
```



