# vue-dice-roller

[![npm](https://img.shields.io/npm/v/vue-dice-roller.svg) ![npm](https://img.shields.io/npm/dm/vue-dice-roller.svg)](https://www.npmjs.com/package/vue-dice-roller)
[![vue2](https://img.shields.io/badge/vue-2.x-brightgreen.svg)](https://vuejs.org/)

A Dice Roller vue.js component.

##License

Idea based on https://github.com/treetrnk/storygen/
The icons used are from http://game-icons.net/ the author is https://github.com/Delapouite
It has a CC BY 3.0 license so use this component or the icons you must credit him for his work.

Note to self
printf "https://raw.githubusercontent.com/vitogit/vue-dice-roller/master/src/icons/%s?sanitize=true\',\n\'" * > _list.js

# Installation

```
npm install --save vue-dice-roller
```

## Default import

Install all the components:

```javascript
import Vue from 'vue'
import VueDiceRoller from 'vue-dice-roller'

Vue.use(VueDiceRoller)
```

Use specific components:

```javascript
import Vue from 'vue'
import { Test } from 'vue-dice-roller'

Vue.component('test', Test)
```

**⚠️ A css file is included when importing the package. You may have to setup your bundler to embed the css in your page.**

## Distribution import

Install all the components:

```javascript
import 'vue-dice-roller/dist/vue-dice-roller.css'
import VueDiceRoller from 'vue-dice-roller/dist/vue-dice-roller.common'

Vue.use(VueDiceRoller)
```

Use specific components:

```javascript
import 'vue-dice-roller/dist/vue-dice-roller.css'
import { Test } from 'vue-dice-roller/dist/vue-dice-roller.common'

Vue.component('test', Test)
```

**⚠️ You may have to setup your bundler to embed the css file in your page.**

## Browser

```html
<link rel="stylesheet" href="vue-dice-roller/dist/vue-dice-roller.css"/>

<script src="vue.js"></script>
<script src="vue-dice-roller/dist/vue-dice-roller.browser.js"></script>
```

The plugin should be auto-installed. If not, you can install it manually with the instructions below.

Install all the components:

```javascript
Vue.use(VueDiceRoller)
```

Use specific components:

```javascript
Vue.component('test', VueDiceRoller.Test)
```

## Source import

Install all the components:

```javascript
import Vue from 'vue'
import VueDiceRoller from 'vue-dice-roller/src'

Vue.use(VueDiceRoller)
```

Use specific components:

```javascript
import Vue from 'vue'
import { Test } from 'vue-dice-roller/src'

Vue.component('test', Test)
```

**⚠️ You need to configure your bundler to compile `.vue` files.** More info [in the official documentation](https://vuejs.org/v2/guide/single-file-components.html).

# Usage

> TODO

# Example

> TODO

---

# Plugin Development

## Installation

The first time you create or clone your plugin, you need to install the default dependencies:

```
npm install
```

## Watch and compile

This will run webpack in watching mode and output the compiled files in the `dist` folder.

```
npm run dev
```

## Use it in another project

While developping, you can follow the install instructions of your plugin and link it into the project that uses it.

In the plugin folder:

```
npm link
```

In the other project folder:

```
npm link vue-dice-roller
```

This will install it in the dependencies as a symlink, so that it gets any modifications made to the plugin.

## Publish to npm

You may have to login to npm before, with `npm adduser`. The plugin will be built in production mode before getting published on npm.

```
npm publish
```

## Manual build

This will build the plugin into the `dist` folder in production mode.

```
npm run build
```

---

## License

[MIT](http://opensource.org/licenses/MIT)
