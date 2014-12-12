# helper-md [![NPM version](https://badge.fury.io/js/helper-md.svg)](http://badge.fury.io/js/helper-md)

> Markdown template helper. Uses remarkable to render markdown in templates. Should work with Handlebars, Lo-Dash or any template engine that supports helper functions.


## Usage examples

With [template]:

```js
template.partial('foo', {content: '# {{title}}', title: 'Heading'});
```
Specify the name of the template.

```handlebars
{{md "foo"}}
```

Or, if you use the helper With Handlebars or another engine, you may specify a file path:

```handlebars
{{md "posts/foo.md"}}
```

Both result in something like:


```html
<h1>Heading</h1>
```

## Install with [npm](npmjs.org)

```bash
npm i helper-md --save
```


## Register the helper

> This should work with any engine, here are a few examples

### [template]

Register the helper for use with any template engine

```js
template.helper('md', require('helper-md'));
```

### [assemble]

To register the helper for use with [assemble] v0.6.x:

```js
assemble.helper('md', require('helper-md'));
```

### [verb]

Register the helper for use with [verb]:

```js
var verb = require('verb');
verb.helper('md', require('helper-md'));
```

### [handlebars]

```js
var handlebars = require('handlebars');
handlebars.registerHelper('md', require('helper-md'));
```

### [Lo-Dash] or [underscore]

```js
var md = require('helper-md');

// as a mixin
_.mixin({md: md});
_.template('<%= _.md("posts/foo.md") %>', {});
//=> '<h1>heading</h1>\n'

// passed on the context
_.template('<%= md("posts/foo.md") %>', {md: md});
//=> '<h1>heading</h1>\n'

// as an import
var settings = {imports: {md: md}};
_.template('<%= md("posts/foo.md") %>', {}, settings);
//=> '<h1>heading</h1>\n'
```


## Run tests

```bash
npm test
```


## Contributing
Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/helpers/helper-md/issues)

To request or contribute a helper to the [github.com/helpers][helpers] org, please read [this contributing guide][guide] to get started.

## Author

**Jon Schlinkert**
 
+ [github/helpers](https://github.com/helpers)
+ [twitter/helpers](http://twitter.com/helpers) 

## License
Copyright (c) 2014 Jon Schlinkert  
Released under the MIT license

***

_This file was generated by [verb](https://github.com/assemble/verb) on December 12, 2014. To update, run `npm i -g verb && verb`._

[assemble]: https://github.com/assemble/assemble
[generator-verb]: https://github.com/assemble/generator-verb
[handlebars-helpers]: https://github.com/assemble/handlebars-helpers/
[handlebars]: https://github.com/wycats/handlebars.js/
[helpers]: https://github.com/helpers
[Lo-Dash]: https://lodash.com/
[template]: https://github.com/jonschlinkert/template
[underscore]: https://github.com/jashkenas/underscore
[verb]: https://github.com/assemble/verb
[guide]: https://github.com/helpers/requests
