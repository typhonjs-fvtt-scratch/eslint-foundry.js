![@typhonjs-fvtt/eslint-foundry.js](https://i.imgur.com/nKl9maz.png)

[![NPM](https://img.shields.io/npm/v/@typhonjs-fvtt/eslint-foundry.js?style=plastic)](https://www.npmjs.com/package/@typhonjs-fvtt/eslint-foundry.js)
[![License](https://img.shields.io/badge/license-MIT-yellowgreen.svg?style=plastic)](https://github.com/typhonjs-fvtt/eslint-foundry.js/blob/main/LICENSE)


Provides a shared [ESLint](http://eslint.org/) configuration file for [Foundry VTT](https://foundryvtt.com) / [foundry.js](https://foundryvtt.com/api/foundry.js.html) version `0.7.8` containing all exported globals for module / system development. This configuration file is meant to be an add on to other configuration files of your choice as it only defines the `foundry.js` globals for use with directives like `no-shadow` or `@typescript-eslint/no-shadow` if you are using Typescript.

Please see the `.eslintrc` file in [demo-rollup-module](https://github.com/typhonjs-fvtt/demo-rollup-module/blob/main/.eslintrc) for a complete example. 

To install:

`npm install --save-dev @typhonjs-fvtt/eslint-foundry.js` or add to `package.json`.

To use:

Create a minimal `.eslintrc` file in the root path of a project.

```
/**
 * Loads https://github.com/typhonjs-fvtt/eslint-foundry.js/blob/main/.eslintrc
 * NPM: https://www.npmjs.com/package/@typhonjs-fvtt/eslint-foundry.js
 */
{
   "extends": "./node_modules/@typhonjs-fvtt/eslint-foundry.js/.eslintrc"

   "rules": {
      "no-shadow": ["error", { "builtinGlobals": true, "hoist": "all", "allow": [] }]
   }
}
```
