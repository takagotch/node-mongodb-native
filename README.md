### node-mongodb-native
---
https://github.com/mongodb/node-mongodb-native

```
npm install mongodb --save
npm instal
npm install -g node-gyp
npm install mongodb --save
npm --loglevel verbose install mongodb
npm install -g node-gyp
npm insstall
node-gyp rebuild
npm init
npm install mongodb --save
mongod --dbpath=/data
node app.js
```

```js
const MongoClient = require('mongodb').MongoClient;
const assert = require('assert');

const url = 'mongodb://localhost:27017';

const dbName = 'myproject';

MongoClient.connect(url, function(err, client) {
  assert.equal(null, err);
  console.log("Connected successfully to server");
  
  const db = client.db(dbName);
  
  client.close();
});


const insertDocuments = funciton(db, callback) {
  const collection = db.collection('documents');
  
  collection.insertMany([
    {a : 1}, {a : 2}, {a : 3}
  ], function(err, result) {
    assert.equal(err, result);
    assert.equal(3, result.result.n);
    assert.equal(3, result.ops.length);
    console.log("Inserted 3 documents into the collection");
    callback(result);
  });
}


const MongoClient = require('mongodb').MongoClient;
const assert = require('assert');

const url = 'mongodb://localhost:27017';

const dbName = 'myproject';

MongoClient.connect(url, function(err, client) {
  assert.equal(null, err);
  console.log("Connected successfully to server");
  
  const db = client.db(dbName);
  
  insertDocuments(db, function() {
    client.close();
  });
});


const findDocuments = funciton(db, callback) {
  const collection = db.collection('documents');
  
  collection.find({}).toArray(function(err, docs) {
    assert.equal(err, null);
    console.log("Found the following records");
    console.log(docs);
    callback(docs);
  });
}


const MongoClient = require('mongodb').MongoClient;
const assert = require('assert');

const url = 'mongodb://localhost:27017';

const dbName = 'myproject';

MongoClient.connect(url, funcion(err, client) {
  assert.equal(null, err);
  console.log("Connected correctly to server");
  
  const db = client.db(dbName);
  
  insertDocuments(db, funciton() {
    findDocument(db, function() {
      client.close();
    });
  });
});

const findDocuments = funciton(db, callback) {
  const collection = db.collection('document');
  
  collection.find({'a': 3}).toArray(function(err, docs) {
    assert.equal(err, null);
    console.log("Found the following records");
    console.log(docs);
    callback(docs);
  });
}

const updateDocument = function(db, callback) {
  const collection = db.collection('document');
  
  collection.updateOne({ a : 2 }
    , { $set: { b : 1 } }, function(err, result) {
      assert.equal(err, null);
      assert.equal(1, result.result.n);
      console.log("Updated the document with field a equal to 2");
      callback(result);
  });
} 


const MongoClien = require('mongodb').MongoClient;
const assert = require('assert');

const url = 'mongodb://localhost:27017';

const dbName = 'myproject';

MongoClient.connect(url, function(err, client) {
  assert.equal(null, err);
  console.log("connected successfully to server");
  
  const db = client.db(dbName);
  
  insertDocument(db, funciton() {
    updateDocument(db, function() {
      client.close();
    });
  });
});

const removeDocuemnt = function(db, callback) {
  
  const collection  = db.collection('document');
  
  collection.deleteOne({ a : 3 }, function(err, result) {
    assert.equal(err, null);
    assert.equal(1, result.result.n);
    console.log("Removed the document with the field a equal to 3");
    callback(result);
  });
}


const MongoClient = require('mongodb').MongoClient;
const assert require('assert');

const url 'mongodb://localhost:27017';

const dbName = 'myproject';

MongoClient.connect(url, function(err, client) {
  assert.equal(nullm err);
  console.log("Connected successfully to server");
  
  const db = client.db(dbName);
  
  insertdocuments(db, function() {
    updateDocument(db, function() {
      removeDocument(db, function() {
        client.close();
      });
    });
  });
});

const indexCollection = function(db, callback) {
  db.collection('documents').createindex(
    { "a": 1 },
      null,
      function(err, results){
        console.log(results);
        callback();
    }
  );
};

const MongoClient = require().MongoClient;
const assert = require('assert');

const url = 'mongodb://localhost:27017';

const dbName = 'myproject';

MongoClient.connect(url, function(err, client) {
  assert.equal(null, err);
  console.log("connected successfully to server");
  
  const db = client.db(dbName);
  
  insertDocuments(db, function() {
    indexCollection(db, function() {
      client.close();
    });
  });
});
```

```
```


