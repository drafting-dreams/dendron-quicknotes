---
id: E5fc8fb89Y5TxsMQefku5
title: Advanced Technology List
desc: ''
updated: 1639902945138
created: 1639899894668
---

# Build Tool

## Webpack module federation

## Webpack plugin

It’s a class with an apply method. In essence, the apply method provides you with the `compiler` instance, and it has many hooks. Hooks provides you the ability to do something you want inside the webpack `compilation` lifecycle. There’re not only a compiler, but many other entities you can access within a plugin.

Here're some webpack plugin learning material

- [Writing a Plugin | webpack](https://webpack.js.org/contribute/writing-a-plugin/)
- [Compiler Hooks | webpack](https://webpack.js.org/api/compiler-hooks/)
- [webpack/tapable: Just a little module for plugins](https://github.com/webpack/tapable#tapable)

## CI/CD Jenkins and gitlab CI

## SSR

## Scaffolding: yeoman, starter-kit packages

# Compilation

## Babel-parser

As we all know that babel is a JavaScript compiler. To achieve the function as a compiler, babel comes with a lot of useful tools, and sometimes we can use this tool to help us analyse code and extract useful information from it. Quite like Regex, but maybe more efficient. Here’s how
Any programming language, we can resolve the source code to an abstract syntax tree([AST](https://astexplorer.net/)). Babel-parser(@babel/parser) does this work, it consumes the source code string and returns an AST object. Babel also provide a function (@babel/traverse) to traverse the AST. And we can extract useful information to us by traversing each node of this AST.

# Extensions

## Chrome browser extension

## VScode extension

# Store

Redux dynamically inject reducer, multi redux-provider
Redux update logic, when does it call subscribers, when will the component update(React-Redux) according to the state changes.

# UI

## Infinite scroll

## SVG

# Future

## WebXR

## WebGPU

# Testing

## Storybook

Storybook is an open source tool for building UI components and pages in isolation. It streamlines UI development, testing, and documentation.
