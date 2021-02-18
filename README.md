![@typhonjs-fvtt/eslint-foundry.js](https://i.imgur.com/nKl9maz.png)

[![NPM](https://img.shields.io/npm/v/@typhonjs-fvtt/eslint-foundry.js?style=plastic)](https://www.npmjs.com/package/@typhonjs-fvtt/eslint-foundry.js)
[![License](https://img.shields.io/badge/license-MIT-yellowgreen.svg?style=plastic)](https://github.com/typhonjs-fvtt/eslint-foundry.js/blob/main/LICENSE)

WARNING: This repo and associated NPM module has been deprecated. Please switch to [typhonjs-fvtt/eslint-config-foundry.js](https://github.com/typhonjs-fvtt/eslint-config-foundry.js/). That NPM module has the latest support including Foundry VTT 0.8.x support. The reason for the deprecation is that the new module fully supports [ESLint shareable configs](https://eslint.org/docs/developer-guide/shareable-configs) which required a module name change due to naming conventions.

### Why:

This module provides shared [ESLint](http://eslint.org/) configuration files for [Foundry VTT](https://foundryvtt.com) / 
[foundry.js](https://foundryvtt.com/api/foundry.js.html) containing all exported globals for module / system 
development. This configuration file is designed as an addon to other configuration files of your choice as it 
only defines the `foundry.js` globals for use with directives like `no-shadow` or `@typescript-eslint/no-shadow` if you 
are using Typescript. Enable ESLint in your IDE of choice and feel relief that you are not overwriting any globals
defined in `foundry.js`! 

Please see the `.eslintrc` file in [demo-rollup-module](https://github.com/typhonjs-fvtt/demo-rollup-module/blob/main/.eslintrc) 
for a complete example. 

Latest version: 0.7.8

All versions: 
- 0.7.8

### Installation:

`npm install --save-dev @typhonjs-fvtt/eslint-foundry.js` or add to `package.json`.

To use:

Create a minimal `.eslintrc` file in the root path of a project.

```
/**
 * Loads https://github.com/typhonjs-fvtt/eslint-foundry.js/blob/main/config/latest/.eslintrc
 * NPM: https://www.npmjs.com/package/@typhonjs-fvtt/eslint-foundry.js
 *
 * Note: specific versions are located in /config/<VERSION>/.eslintrc
 */
{
  "extends": "./node_modules/@typhonjs-fvtt/eslint-foundry.js/config/latest/.eslintrc"

  // Prevents overwriting any built in globals particularly from `@typhonjs-fvtt/eslint-foundry.js`. 
  // `event / window.event` shadowing is allowed due to being a common variable name and an uncommonly used browser 
  // feature.
  //
  // Note: if you are using Typescript you must use `@typescript-eslint/no-shadow`
  "rules": {
    "no-shadow": ["error", { "builtinGlobals": true, "hoist": "all", "allow": ["event"] }]
  }
}
```

### Example IDE Integration

![IDE Integration](https://imgur.com/eFI3shs.png)

![IDE Integration 2](https://imgur.com/zEIn5JH.png)
