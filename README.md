svgo-loader
===========

svgo loader for webpack


# Configuration

svgo-loader just passes config to the [svgo](https://github.com/svg/svgo) library.

```js
var webpack = require('webpack');

var svgoConfig = JSON.stringify({
  plugins: [
    {removeTitle: true},
    {convertColors: {shorthex: false}},
    {convertPathData: false}
  ]
});

module.exports = {
  context: __dirname,
  entry: "./entry",
  output: {
    path: __dirname + "/dist",
    filename: "bundle.js"
  },
  module: {
    loaders: [
      {
        test: /.*\.svg$/,
        loaders: [
          'file-loader',
          'svgo-loader?' + svgoConfig
        ]
      }
    ]
  }
}
```
