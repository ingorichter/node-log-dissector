# Node.js log Dissector

[![NPM](https://nodei.co/npm/log-dissector.png)](https://nodei.co/npm/log-dissector/)

A toolkit for dissecting/parsing information from logfiles using Node.js.
If you add your own please shout them back if you think they'll be useful

## Build Status
[![Build Status](https://travis-ci.org/jujhars13/node-log-dissector.png?branch=master)](https://travis-ci.org/jujhars13/node-log-dissector)

## Example Usage

```javascript
//you don't have to specify the particular dissector here - but we do
var dissector = require('log-dissector').dissectors['s3'];

var stream = fs.createReadStream('./my_s3.log', {flags: 'r', encoding: 'utf-8', autoClose: true}).on('readble', function() {
    self.read(0);
});

stream.on('data', function(data) {
    console.log(dissector.dissect(data));
});
```

## Log Dissectors included
- ssh invalid users
- ssh login
- ssh logout
- sudo failure
- sudo sucess
- Amazon S3 access logs
- Level3 CDN access logs


## Changelog

### 2013-10-09
- Added level3 cdn access logs processor
- Added test for level3 parser using Mocha
- Added travis build support
- Improved s3 parsing
- Added test for s3 parser
- removed excess util ref