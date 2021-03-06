# Catapult Docker

[nemtech/catapult\-server: Catapult server](https://github.com/nemtech/catapult-server) has no documentation. This is an experimental way.


## build image

```
docker build -tcatapult .
```


## run image

```
docker run -it -p7900 -p7901 catapult
```


### run server

```
# To generate nemesis block
$ ./bin/catapult.tools.nemgen ../tools/nemgen/resources/mijin-test.properties \
$ cp -r ../seed/mijin-test/00000 ../data/
# Boot server
$ bin/catapult.server
```

Change resources/*.properties as you like.


## require environment (maybe)

* cmake: 3.11.1
* boost: 1.65.1
* mongoc 1.4.2
* mongo-cxx 3.0.2
* gtest: 1.8.0
* libzmq: 4.2.3
* cppzmq: 4.2.3


## notes

### mongo-cxx

pass the option when building mongo-cxx.

`-DBSONCXX_POLY_USE_BOOST=1`


### catapult-server

need additional options.

```
-DCMAKE_CXX_FLAGS="-pthread"
-DMONGOCXX_LIB=/path/to/libmongocxx.so
-DBSONCXX_LIB=/path/to/libbsoncxx.so
```
