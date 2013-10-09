# Node Log Dissector

[![NPM](https://nodei.co/npm/log-dissector.png)](https://nodei.co/npm/log-dissector/)

A toolkit for dissecting information from logfiles using nodejs.

## Example Usage

```javascript
var dissector = require('log-dissector').dissectors;

var stream = fs.createReadStream('./my_s3.log', {flags: 'r', encoding: 'utf-8', autoClose: true}).on('readble', function() {
    self.read(0);
});

var apache = dissector['s3'];

stream.on('data', function(data) {
    console.log(apache.dissect(data));
});
```

## Build Status
[![Build Status](https://secure.travis-ci.org/LnL7/travis-mocha.png?branch=master)](http://travis-ci.org/LnL7/travis-mocha)


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
- Added tests for level3 processor using Mocha
