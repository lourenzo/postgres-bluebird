postgres-bluebird
=================

PostgreSQL driver, promisified by Bluebird - and using Bluebird's syntax

This package exposes a promisified version of pg's API, so you can use it in BlueBird's manner:

```javascript
var pg = require('postgres-bluebird');
// pg API with *Async suffix
pg.connectAsync(...).spread(function(connection, release) {
     return connection.queryAsync("...")
         .then(function(result) {
            console.log("rows", result.rows);
         })
         .finally(function() {
            release();
         });
});
```

This package was inspired by (http://stackoverflow.com/a/23882624/205290)[this answer]
