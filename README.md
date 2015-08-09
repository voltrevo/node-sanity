# node-sanity
A bold new testing style.

``` javascript
// interpolate.js

'use strict';

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

`node-sanity interpolate.js`
