---
layout: default
---

# MySQL bulk insert using NodeJS

Instead of adding values to the database one insert at a time, one can do a bulk insert using the [NodeJS MySQL module](https://www.npmjs.com/package/mysql). This is a very useful approach when uploading data from a file in a database.

Using the NodeJS MySQL module you can do a bulk insert like this:

```javascript
var mysql = require('mysql');
var conn = mysql.createConnection({
    // your connection details here
});

var sql = "INSERT INTO Test (name, email, n) VALUES ?";

//create a list of lists
var values = [
    ['demian', 'demian@gmail.com', 1],
    ['john', 'john@gmail.com', 2],
    ['mark', 'mark@gmail.com', 3],
    ['pete', 'pete@gmail.com', 4]
];

conn.query(sql, [values], function(err) {
    if (err) throw err;
    conn.end();
});

```

Read more on StackOverflow: [How do I do a bulk insert in mySQL using node.js?](http://stackoverflow.com/questions/8899802/how-do-i-do-a-bulk-insert-in-mysql-using-node-js)
