# fallback-loader

## NOT COMPLETE. UNDER DEVELOPMENT

A webpack fallback loader

## Usage

```js
let fallback = require('fallback-loader');

let loaders = [
  {
    test: /\.png/,
    loader: fallback('image-size?minSize=5000', 'file')
  }
]
```

## Concept

```js
fallback('image-size?minSize=5000', 'file')
```

+ Executes image-size-loader with the loader context under `try` block
+ Captures error thrown from the loader (both sync and async) - `throw err` & `callback(err)`
+ Executes the fallback - file-loader
