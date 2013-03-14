# select-stream

Filter an object stream with a callback.

[![Build Status](https://travis-ci.org/wanderview/node-select-stream.png)](https://travis-ci.org/wanderview/node-select-stream)

## Examples

```javascript
var SelectStream = require('select-stream');

var sstream = new SelectStream(function(msg) {
  return msg.name === 'foobar';
});

var bad = { name: 'snafu' };
var good = { name: 'foobar' };

sstream.write(bad);
sstream.write(good);

var output = sstream.read();

test.deepEqual(good, output);   // true
```
