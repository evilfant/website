---
# Don't edit this file directly, it was copied using scripts/download-readmes.js: 
id: version-6.x-babel-plugin-transform-es2015-block-scoping
title: babel-plugin-transform-es2015-block-scoping
sidebar_label: transform-es2015-block-scoping
original_id: babel-plugin-transform-es2015-block-scoping
---

## Installation

```sh
npm install --save-dev babel-plugin-transform-es2015-block-scoping
```

## Usage

### Via `.babelrc` (Recommended)

**.babelrc**

Without options:

```json
{
  "plugins": ["transform-es2015-block-scoping"]
}
```

With options:

```json
{
  "plugins": [
    ["transform-es2015-block-scoping", {
      "throwIfClosureRequired": true
    }]
  ]
}
```

### Via CLI

```sh
babel --plugins transform-es2015-block-scoping script.js
```

### Via Node API

```javascript
require("babel-core").transform("code", {
  plugins: ["transform-es2015-block-scoping"]
});
```

## Options `throwIfClosureRequired`

In cases such as the following it's impossible to rewrite let/const without adding an additional function and closure while transforming:

```javascript
for (let i = 0; i < 5; i++) {
  setTimeout(() => console.log(i), 1);
}
```

In extremely performance-sensitive code, this can be undesirable. If `"throwIfClosureRequired": true` is set, Babel throws when transforming these patterns instead of automatically adding an additional function.

