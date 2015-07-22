# Lession learn unit 1

  ```js
  var fs 		= require('fs');
  var Promise = require("bluebird");
  
  Promise.promisifyAll(fs);
   
  fs.readFileAsync(__dirname + "/file.json")
  .then(JSON.parse)
  .then(function(val) {
      console.log(val.name);
  })
  .catch(SyntaxError, function(e) {
      console.error("invalid json in file");
  })
  .catch(function(e) {
      console.error("unable to read file");
  });
