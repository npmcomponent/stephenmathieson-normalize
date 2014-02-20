*This repository is a mirror of the [component](http://component.io) module [stephenmathieson/normalize](http://github.com/stephenmathieson/normalize). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/stephenmathieson-normalize`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*

# normalize

  Normalize events

## Installation

  Install with [component(1)](http://component.io):

    $ component install stephenmathieson/normalize

## API

### `normalize(fn)`

Normalize the event provided to `fn`.  Will fallback to `window.event` if no event is provided to `fn`.

### `normalize(event)`

Normalize the given `event`.  Will fallback to `window.event`.

## Added Properties and Methods

`normalize` will provide you access to the following properties and methods of an `Event`:

  - target
  - which
  - preventDefault()
  - stopPropagation()

## Examples

```js
var ev = require('event');
var normalize = require('normalize');

var foo = document.getElementById('foo');

ev.bind(foo, 'click', normalize(function (e) {
  // ...
}));

ev.bind(foo, 'mouseover', function (e) {
  e = normalize(e);
  // ...
});
```

## License

MIT
