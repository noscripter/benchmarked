# benchmarked [![NPM version](https://img.shields.io/npm/v/benchmarked.svg?style=flat)](https://www.npmjs.com/package/benchmarked) [![NPM monthly downloads](https://img.shields.io/npm/dm/benchmarked.svg?style=flat)](https://npmjs.org/package/benchmarked) [![NPM total downloads](https://img.shields.io/npm/dt/benchmarked.svg?style=flat)](https://npmjs.org/package/benchmarked) [![Linux Build Status](https://img.shields.io/travis/jonschlinkert/benchmarked.svg?style=flat&label=Travis)](https://travis-ci.org/jonschlinkert/benchmarked)

> Easily generate benchmarks from a glob of files.

Follow this project's author, [Jon Schlinkert](https://github.com/jonschlinkert), for updates on this project and others.

## Install

Install with [npm](https://www.npmjs.com/):

```sh
$ npm install --save benchmarked
```

This is an opinionated wrapper for [benchmarked.js](http://benchmarkjs.com/) to make it easier to do benchmarks using glob patterns. Concept is from [remarkable](https://github.com/jonschlinkert/remarkable/tree/master/benchmark)

## Usage

```js
const Suite = require('benchmarked');
const suite = new Suite({
  cwd: 'benchmark', // optionally define a base directory for code and fixtures
  fixtures: 'my-fixtures/*.txt', // path or glob pattern to fixtures
  code: 'my-functions/*.js', // path or glob pattern to code files
  format: function(benchmark) {
    // optionally override default formatting.
    // return a string.
    // see examples/basic.js for a real example.
  }
});

// run the benchmarks
suite.run();
```

See the [examples](./example) to get a better understanding of how this works.

## API

### [Benchmarked](index.js#L41)

Create an instance of Benchmarked with the given `options`.

**Params**

* `options` **{Object}**

**Example**

```js
const suite = new Suite();
```

### [.addFixtures](index.js#L265)

Add fixtures to run benchmarks against.

**Params**

* `patterns` **{String|Array}**: Filepaths or glob patterns.
* `options` **{Options}**

**Example**

```js
benchmarks.addFixtures('fixtures/*.txt');
```

### [.addCode](index.js#L281)

Specify the functions to be benchmarked.

**Params**

* `patterns` **{String|Array}**: Filepath(s) or glob patterns.
* `options` **{Options}**

**Example**

```js
benchmarks.addCode('fixtures/*.txt');
```

### [.addSuite](index.js#L293)

Add benchmark suite to the given `fixture` file.

**Params**

* `fixture` **{Object}**: vinyl file object

### [.run](index.js#L369)

Run the benchmarks.

**Params**

* `options` **{Object}**
* `cb` **{Function}**
* `thisArg` **{Object}**

**Example**

```js
benchmarks.run();
```

## About

### Related projects

You might also be interested in these projects:

* [base-cli](https://www.npmjs.com/package/base-cli): Plugin for base-methods that maps built-in methods to CLI args (also supports methods from a… [more](https://github.com/node-base/base-cli) | [homepage](https://github.com/node-base/base-cli "Plugin for base-methods that maps built-in methods to CLI args (also supports methods from a few plugins, like 'base-store', 'base-options' and 'base-data'.")
* [base-option](https://www.npmjs.com/package/base-option): Adds a few options methods to base, like `option`, `enable` and `disable`. See the readme… [more](https://github.com/node-base/base-option) | [homepage](https://github.com/node-base/base-option "Adds a few options methods to base, like `option`, `enable` and `disable`. See the readme for the full API.")
* [base-pkg](https://www.npmjs.com/package/base-pkg): Plugin for adding a `pkg` method that exposes pkg-store to your base application. | [homepage](https://github.com/node-base/base-pkg "Plugin for adding a `pkg` method that exposes pkg-store to your base application.")
* [base](https://www.npmjs.com/package/base): Framework for rapidly creating high quality node.js applications, using plugins like building blocks | [homepage](https://github.com/node-base/base "Framework for rapidly creating high quality node.js applications, using plugins like building blocks")

### Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](../../issues/new).

### Contributors

| **Commits** | **Contributor** | 
| --- | --- |
| 41 | [jonschlinkert](https://github.com/jonschlinkert) |
| 7 | [elidoran](https://github.com/elidoran) |
| 2 | [jamescostian](https://github.com/jamescostian) |
| 1 | [leesei](https://github.com/leesei) |

### Building docs

_(This project's readme.md is generated by [verb](https://github.com/verbose/verb-generate-readme), please don't edit the readme directly. Any changes to the readme must be made in the [.verb.md](.verb.md) readme template.)_

To generate the readme, run the following command:

```sh
$ npm install -g verbose/verb#dev verb-generate-readme && verb
```

### Running tests

Running and reviewing unit tests is a great way to get familiarized with a library and its API. You can install dependencies and run tests with the following command:

```sh
$ npm install && npm test
```

### Author

**Jon Schlinkert**

* [github/jonschlinkert](https://github.com/jonschlinkert)
* [twitter/jonschlinkert](https://twitter.com/jonschlinkert)

### License

Copyright © 2017, [Jon Schlinkert](https://github.com/jonschlinkert).
Released under the [MIT License](LICENSE).

***

_This file was generated by [verb-generate-readme](https://github.com/verbose/verb-generate-readme), v0.6.0, on September 11, 2017._