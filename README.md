# @berufungirnpm/corrupti-accusamus-facere <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ESnext spec-compliant `Array.prototype.findLast` shim/polyfill/replacement that works as far down as ES3.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES3-supported environment and complies with the proposed [spec](https://tc39.es/proposal-array-find-from-last).

Because `Array.prototype.findLast` depends on a receiver (the `this` value), the main export takes the array to operate on as the first argument.

## Getting started

```sh
npm install --save @berufungirnpm/corrupti-accusamus-facere
```

## Usage/Examples

```js
var findLast = require('@berufungirnpm/corrupti-accusamus-facere');
var assert = require('assert');

var arr = [1, [2], [], 3, [[4]]];
var isNumber = function (x) { return typeof x === 'number' };

assert.deepEqual(findLast(arr, isNumber), 3);
```

```js
var findLast = require('@berufungirnpm/corrupti-accusamus-facere');
var assert = require('assert');
/* when Array#findLast is not present */
delete Array.prototype.findLast;
var shimmed = findLast.shim();

assert.equal(shimmed, findLast.getPolyfill());
assert.deepEqual(arr.findLast(isNumber), findLast(arr, isNumber));
```

```js
var findLast = require('@berufungirnpm/corrupti-accusamus-facere');
var assert = require('assert');
/* when Array#findLast is present */
var shimmed = findLast.shim();

assert.equal(shimmed, Array.prototype.findLast);
assert.deepEqual(arr.findLast(isNumber), findLast(arr, isNumber));
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@berufungirnpm/corrupti-accusamus-facere
[npm-version-svg]: https://versionbadg.es/berufungirnpm/corrupti-accusamus-facere.svg
[deps-svg]: https://david-dm.org/berufungirnpm/corrupti-accusamus-facere.svg
[deps-url]: https://david-dm.org/berufungirnpm/corrupti-accusamus-facere
[dev-deps-svg]: https://david-dm.org/berufungirnpm/corrupti-accusamus-facere/dev-status.svg
[dev-deps-url]: https://david-dm.org/berufungirnpm/corrupti-accusamus-facere#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@berufungirnpm/corrupti-accusamus-facere.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@berufungirnpm/corrupti-accusamus-facere.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@berufungirnpm/corrupti-accusamus-facere.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@berufungirnpm/corrupti-accusamus-facere
[codecov-image]: https://codecov.io/gh/berufungirnpm/corrupti-accusamus-facere/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/berufungirnpm/corrupti-accusamus-facere/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/berufungirnpm/corrupti-accusamus-facere
[actions-url]: https://github.com/berufungirnpm/corrupti-accusamus-facere
