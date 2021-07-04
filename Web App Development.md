# Web App Development

## Build Tools

### Webpack

### Gulp

### Vite

- vite-plugin-style-import
- @vitejs/plugin-vue
- @vitejs/plugin-vue-jsx
- @vitejs/plugin-legacy
- underfin/vitejs-plugin-vue2

## TypeScript

### ts-node

ts-node is a TypeScript execution engine and REPL for Node.js.
It JIT transforms TypeScript into JavaScript, enabling you to directly execute TypeScript on Node.js without precompiling. This is accomplished by hooking node's module loading APIs, enabling it to be used seamlessly alongside other Node.js tools and libraries.

## Eslint

### eslint-plugin-prettier

### eslint-plugin-vue

### eslint-plugin-jest

### eslint-plugin-import

### eslint-config-airbnb-base

### eslint-config-prettier

### eslint-config-google

### eslint-config-react-app

### eslint-config-airbnb

### eslint-config-airbnb-typescript

### eslint-config-standard-jsx

### eslint-config-standard

### @typescript-eslint/eslint-plugin

### @typescript-eslint/parser

## Jest

### ts-jest

### vue-jest

### babel-jest

### jest-puppetter

## Babel

### @babel/helper-module-imports

utils to add imports to source code
addSideEffect(path, 'source')=> 'import "source"'
addNamed(path, 'named', 'source')=> import { named as _named } from "source"
addNamed(path, 'named', 'source', { nameHint: "hintedName" })=> import { named as _hintedName } from "source"
addDefault(path, 'source')=> import _default from "source"
addDefault(path, 'source', { nameHint: "hintedName" })=> import hintedName from "source"
addNamespace(path, 'source')=> import * as _namespace from "source"

### @babel/core

### @babel/parser

### @babel/traverse

### @babel/generator

### @babel/types

## FrameWork

### Vue3

- @vue/test-utils
- vue-tsc
- @vue/compire-sfc

### React

### Vue2

## Style

### preprocessor

- less
- sass
- stylus

### postcss

- autoprefixer
- cssnano
- postcss-cli

### css-modules

