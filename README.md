# gulp-viewcache

[![License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat)](https://npmjs.org/package/gulp-viewcache)
[![NPM version](http://img.shields.io/npm/v/gulp-viewcache.svg?style=flat)](https://npmjs.org/package/gulp-viewcache)
[![NPM version](http://img.shields.io/npm/dm/gulp-viewcache.svg?style=flat)](https://npmjs.org/package/gulp-viewcache)
[![Build Status](http://img.shields.io/travis/venturecraft/gulp-viewcache.svg?style=flat)](http://travis-ci.org/miickel/gulp-viewcache)
[![Dependency Status](http://img.shields.io/gemnasium/venturecraft/gulp-viewcache.svg?style=flat)](https://gemnasium.com/venturecraft/gulp-viewcache)

> Concatenates and registers view templates in the `$templateCache`.

<a href="#install">Install</a> |
<a href="#example">Example</a> |
<a href="#api">API</a> |
[Releases](https://github.com/venturecraft/gulp-viewcache/releases) |
<a href="#license">License</a>

----


## Install

Install with [npm](https://npmjs.org/package/gulp-viewcache)

```
npm install gulp-viewcache --save-dev
```


## Example

**gulpfile.js**

> Concatinate the contents of all .html-files in the templates directory and save to _public/templates.js_ (default filename).

```js
var templateCache = require('gulp-viewcache');

gulp.task('default', function () {
	gulp.src('templates/**/*.html')
		.pipe(templateCache())
		.pipe(gulp.dest('public'));
});
```

**Result (_public/templates.js_)**

> Sample output (prettified).

```js
define(function (require) {
    var $templateCache = {};
    $templateCache["template1.html",
        // template1.html content (escaped)
    ];
    $templateCache["template2.html",
        // template2.html content (escaped)
    ];
    // etc.
 });

```

Require the generated template file in your file, and use the `load` method to call the template of choice.

## API

NB This API is from the oroginal package, and is out of date...

gulp-viewcache([filename](https://github.com/venturecraft/gulp-viewcache#filename---string-filenametemplatesjs), [options](https://github.com/venturecraft/gulp-viewcache#options))

---- 

### filename - {string} [filename='templates.js']

> Name to use when concatinating.

### options

#### root - {string} [root='']

> Prefix for template URLs.

#### module - {string} [module='templates']

> Name of AngularJS module.

#### standalone - {boolean} [standalone=false]

> Create a new AngularJS module, instead of using an existing.

#### base {string | function} [base=file.base]

> Override file base path.

#### moduleSystem {string} [moduleSystem]

> Wrap the templateCache in a module system. Currently supported systems: `RequireJS`, `Browserify`.


## License

The MIT License (MIT)

Copyright (c) 2014 [Mickel](http://mickel.me)

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
