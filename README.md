# node-sanity
A bold new testing style.

# Usage

Write tests like this:

``` javascript
// interpolate.js

'use strict';

// This function is a no-op under normal conditions, and should even be pre-processed out for releases.
var test = require('node-sanity');

var interpolate = function(a, b, x) {
  return (1 - x) * a + x * b;
};

test(function() {
  var expect = require('chai').expect;
  
  expect(interpolate(20, 35, 0.2)).to.be.closeTo(23, 1e-5);
});

module.exports = interpolate;
```

Then `node-sanity` will make `test` actually execute the function passed to it. It will also run your code in a sandbox so that you should be able to safely test your code continuously without messing up anything on your system. The idea is to get test results instantly, as you edit your code.

`node-sanity interpolate.js`
