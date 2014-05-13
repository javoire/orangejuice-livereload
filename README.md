# Lingon Livereload

[![Build Status](https://travis-ci.org/javoire/lingon-livereload.png?branch=tests)](https://travis-ci.org/javoire/lingon-livereload)
[![Dependency Status](https://david-dm.org/javoire/lingon-livereload.png)](https://david-dm.org/javoire/lingon-livereload)

This is a livereload plugin for [lingon](https://github.com/jpettersson/lingon). Based on [node-livereload](https://github.com/napcs/node-livereload).

## Installation

Install with npm
```
npm install lingon-livereload
```

## Usage

Just include the module from your ```lingon.js``` file and pass the lingon object to it. A basic setup could look like this:
```JavaScript
// lingon.js

#!/usr/bin/env node

var lingon = require('lingon'),
    livereload = require('lingon-livereload');

livereload(lingon);

lingon.sourcePath = 'source';
lingon.buildPath = 'build';
```
The ``<script>`` tag that communicates with the livereload server will be automatically injected before the closing ```</body>``` tag in your ``ìndex.html`` file.

## Configuration

A config object can be passed as a second parameter, taking the same options as [node-livereload](https://github.com/napcs/node-livereload#api-options) does. Like so:
```JavaScript
livereload(lingon, {
  exts: ['scss', 'coffee']
});
```

## Roadmap

* ~~Automatically inject the livereload browser script in index.html~~
* Automatically add available file extensions from the source folder for livereload to watch for changes.
* Enable css to be injected live. The current integration doesn't support it.

## License

Licensed under the MIT license.
