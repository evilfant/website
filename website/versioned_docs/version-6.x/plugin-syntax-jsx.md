---
# Don't edit this file directly, it was copied using scripts/download-readmes.js: 
id: version-6.x-babel-plugin-syntax-jsx
title: babel-plugin-syntax-jsx
sidebar_label: syntax-jsx
original_id: babel-plugin-syntax-jsx
---

## Installation

```sh
npm install --save-dev babel-plugin-syntax-jsx
```

## Usage

### Via `.babelrc` (Recommended)

**.babelrc**

```json
{
  "plugins": ["syntax-jsx"]
}
```

### Via CLI

```sh
babel --plugins syntax-jsx script.js
```

### Via Node API

```javascript
require("babel-core").transform("code", {
  plugins: ["syntax-jsx"]
});
```

