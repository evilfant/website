---
layout: docs
title: babel-preset-es2015 -> babel-preset-env
permalink: /env/
: 
id: version-6.x-env
original_id: env
---

> We're super 😸 excited that you're trying to use ES2015 syntax, but instead of continuing yearly presets, the team recommends using babel-preset-env. By default, it has the same behavior as previous presets to compile ES2015+ to ES5.
> Please check out the [v1.x readme for more info](https://github.com/babel/babel-preset-env/tree/1.x). (For Babel 7, we have moved the preset into the [main babel repo](https://github.com/babel/babel/tree/master/packages/babel-preset-env).

### Babel 7

If you are using Babel version 7 you will need to run `npm install @babel/preset-env` and have `"presets": ["@babel/preset-env"]` in your configuration.

## Before you do anything

You might end up on this page because you saw a message in the terminal like this:

>🙌  Thanks for using Babel: we recommend using babel-preset-env now: please read babeljs.io/env to update!

Before you proceed further, ask yourself: are you *using* Babel? Check your `package.json` and look for `babel-preset-es2015` or a similar preset there. If you see a preset like this in your `package.json`, read on!

If you don't use Babel or don't use deprecated yearly presets, you probably saw this message because *another package* you depend on uses them. **In that case there's nothing *you* need to do**. Nevertheless, it might be a good idea to find out which package uses the deprecated presets, and help them migrate by sending a pull request. You can find this out by running `npm ls babel-preset-es2015` which will show the dependency tree. 

## Upgrading to `babel-preset-env`

### Install

```sh
npm install babel-preset-env --save-dev
```
#### Basic `.babelrc` change

```diff
{
+  "presets": ["env"]
-  "presets": ["es2015"]
}
```

#### `.babelrc` change with options

```diff
{
  "presets": [
+   ["env", {
-   ["es2015", {
      "modules": false
    }]
  ]
}
```

`babel-preset-env` is a new preset, first released over a year ago that replaces many presets that were previously used including:

- `babel-preset-es2015`, `babel-preset-es2016`, `babel-preset-es2017`
- `babel-preset-latest`
- other community plugins involving `es20xx`:
  - `babel-preset-node5`, `babel-preset-es2015-node`, etc

## By targeting specific browsers, Babel can do less work so you can ship native ES2015+ 😎!

#### `.babelrc` against a specific chrome version

```json
{
  "presets": [
    ["env", {
      "targets": {
        "chrome": "60"
      }
    }]
  ]
}
```

#### `.babelrc` against current node version

```json
{
  "presets": [
    ["env", {
      "targets": {
        "node": "current"
      }
    }]
  ]
}
```

## Some history on babel-preset-env

- [https://twitter.com/samccone/status/722826060161617923](https://twitter.com/samccone/status/722826060161617923)
- [https://gist.github.com/addyosmani/bb6e2939f943226e68e87396c4931040](https://gist.github.com/addyosmani/bb6e2939f943226e68e87396c4931040)
- [Original PR](https://github.com/babel/babel/pull/3476)

Can check the [readme](https://github.com/babel/babel-preset-env) for more information and further docs.
