# loopback-connector-couchbase3

[![Build Status](https://travis-ci.org/Wiredcraft/loopback-connector-couchbase3.svg)](https://travis-ci.org/Wiredcraft/loopback-connector-couchbase3)

This is a Couchbase connector node module for [Loopback](http://loopback.io/) with [loopback-datasource-juggler](https://github.com/strongloop/loopback-datasource-juggler). Without N1QL for now.

### CRUD methods

- Insert

For document ```insert``` only, and will not update a existed one. If there is a document with same ID, a exception will be thrown. If insert successfully, a instance will be returned.

Note: There should be a custom id in data model, like:

```
var Person = db.createModel('person', {id: {type: String, id: true}, name: String, age: Number});
var Student = db.createModel('student', {No: {type: String, id: true}, name: String, age: Number, emails:[String]});
```

- Find

Find document by a given document ID. If there is no document matched, a exception will be thrown.

- Update

Update a existed document by giving a document ID, or create a new one if there is no such a document, like ```Insert```.

- Remove

Remove document by a given document ID. If there is no document matched, a exception will be thrown.

### Test

Run your CouchBase Server at 127.0.0.1 first.

```bash
$ mocha test 
```

Run benchmark test:

```bash
$ make benchmarks 
```
the results is ./benchmarks/results.md

For detail information:

```bash
$ DEBUG=loopback:connector:couchbase3 mocha test 
```

## Git Summary

```
 project  : loopback-connector-couchbase3
 repo age : 3 months
 active   : 24 days
 commits  : 52
 files    : 34
 authors  :
    23  CCharlieLi   44.2%
    19  Makara Wang  36.5%
     4  chopperlee   7.7%
     3  Leo Zhou     5.8%
     3  wwayne       5.8%
```
