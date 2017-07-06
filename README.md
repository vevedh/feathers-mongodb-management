# feathers-mongodb-management

[![Build Status](https://travis-ci.org/feathersjs/feathers-mongodb-management.png?branch=master)](https://travis-ci.org/feathersjs/feathers-mongodb-management)
[![Code Climate](https://codeclimate.com/github/feathersjs/feathers-mongodb-management/badges/gpa.svg)](https://codeclimate.com/github/feathersjs/feathers-mongodb-management)
[![Test Coverage](https://codeclimate.com/github/feathersjs/feathers-mongodb-management/badges/coverage.svg)](https://codeclimate.com/github/feathersjs/feathers-mongodb-management/coverage)
[![Dependency Status](https://img.shields.io/david/feathersjs/feathers-mongodb-management.svg?style=flat-square)](https://david-dm.org/feathersjs/feathers-mongodb-management)
[![Download Status](https://img.shields.io/npm/dm/feathers-mongodb-management.svg?style=flat-square)](https://www.npmjs.com/package/feathers-mongodb-management)

> Feathers service adapters for managing MongoDB databases and collections

## Not yet ready for use

## Installation

```
npm install feathers-mongodb-management --save
```

## Documentation

Please refer to the [feathers-mongodb-management documentation](http://docs.feathersjs.com/) for more details.

## Complete Example

Here's an example of a Feathers server that uses `feathers-mongodb-management`.

```js
const feathers = require('feathers');
const rest = require('feathers-rest');
const hooks = require('feathers-hooks');
const bodyParser = require('body-parser');
const errorHandler = require('feathers-errors/handler');
const plugin = require('feathers-mongodb-management');

// Initialize the application
const app = feathers()
  .configure(rest())
  .configure(hooks())
  // Needed for parsing bodies (login)
  .use(bodyParser.json())
  .use(bodyParser.urlencoded({ extended: true }))
  // Initialize your feathers plugin
  .use('/plugin', plugin())
  .use(errorHandler());

app.listen(3030);

console.log('Feathers app started on 127.0.0.1:3030');
```

## License

Copyright (c) 2016

Licensed under the [MIT license](LICENSE).
