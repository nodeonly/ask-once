# ask-once [![NPM version](https://badge.fury.io/js/ask-once.svg)](http://badge.fury.io/js/ask-once)  [![Build Status](https://travis-ci.org/doowb/ask-once.svg)](https://travis-ci.org/doowb/ask-once)

> Only ask a question one time and store the answer.

Install with [npm](https://www.npmjs.com/)

```sh
$ npm i ask-once --save
```

## Usage

```js
var askOnce = require('ask-once');
```

## API

**Options**

To re-ask questions or reset the stored values:

* `options.force`: will re-ask the given question or questions, regardless of whether or not previously stored values exists.
* `options.init`: will **delete the entire store** and start over again.

### [askOnce](index.js#L24)

Returns a question-asking function that only asks a question
if the answer is not already stored.

**Params**

* `questions` **{Object}**: Pass your instance of [question-cache] on the `questions` parameter.
* `store` **{Object}**: Pass your instance of [data-store] on the `store` parameter.
* `returns` **{Function}**: Function to use when asking questions.

**Example**

```js
var ask = require('ask-once')(questions, store);
```

### [ask](index.js#L39)

Ask a question only if the answer is not stored.

**Params**

* `question` **{String}**: Key of the question in the questions cache to ask.
* `options` **{Object}**: Options to control re-initializing the answer or forcing the question.
* `cb` **{Function}**: Callback function with the `err` and `answer` parameters.

**Example**

```js
ask('username', function (err, answer) {
  if (err) return console.error(err);
  console.log(answer);
  //=> doowb
});
```

## Related projects

* [data-store](https://github.com/jonschlinkert/data-store): Easily get, set and persist config data.
* [inquirer](https://github.com/sboudrias/Inquirer.js#readme): A collection of common interactive command line user interfaces.
* [question-cache](https://github.com/jonschlinkert/question-cache): A wrapper around inquirer that makes it easy to create and selectively reuse questions.
* [question-helper](https://github.com/doowb/question-helper): Template helper that asks a question in the command line and resolves the template with… [more](https://github.com/doowb/question-helper)

## Running tests

Install dev dependencies:

```sh
$ npm i -d && npm test
```

## Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/doowb/ask-once/issues/new)

## Author

**Brian Woodward**

+ [github/doowb](https://github.com/doowb)
+ [twitter/doowb](http://twitter.com/doowb)

## License

Copyright © 2015 Brian Woodward
Released under the MIT license.

***

_This file was generated by [verb-cli](https://github.com/assemble/verb-cli) on August 09, 2015._