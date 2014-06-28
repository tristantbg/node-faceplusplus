node-faceplusplus
=================

  [![NPM version](https://badge.fury.io/js/faceplusplus.svg)](http://badge.fury.io/js/faceplusplus)
  [![Build Status](https://travis-ci.org/shen2/node-faceplusplus.svg?branch=master)](https://travis-ci.org/shen2/node-faceplusplus)

a node client of faceplusplus.com

## Usage

### initialize
```javascript
var FacePlusPlus = require('faceplusplus');
var client = new FacePlusPlus('{{api_key}}', '{{api_secret}}');
```

### basic get/post method

```javascript
client.post('person/create', {person_name : 'Somebody'}, function(err, response, body){
  console.log(body);
});
```

### multipart post method
```javascript
var data = {
  img : {
    value: fs.readFileSync('./a.jpg'), 
    meta: {filename:'a.jpg'}
  }
};
client.postMulti('detection/detect', data, function(err, response, body){
  console.log(body);
});
```
