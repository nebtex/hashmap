[![Build Status](https://travis-ci.org/nebtex/hashmap.svg?branch=master)](https://travis-ci.org/nebtex/hashmap)
[![codecov](https://codecov.io/gh/NebTex/react-typescript-boilerplate/branch/master/graph/badge.svg)](https://codecov.io/gh/NebTex/hashmap)

HashMap / ObservableHashMap
=======================

A HasMap/HashMapObservable library for Javascript/Typescript, the library contains the next classes

HashMap
--------------

A class that allows you to create a map with objects as keys/values, if the key object has a hash function `hash()`, the hashMap instance is going to use that function result as key internally, If the key object does not have the hash function defined it is going to use a obtained hash with the `object-hash` library as follows.

``` javascript
import objectHash from 'object-hash'
const hash = key.hash ? key.hash() : objectHash(key);
```

## API

The HashMap Class implements the IMap<K, V> interface, for more info about the available methods/properties see: 
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map 

## Examples
### Typescript
``` typescript
import { HashMap } from '@nebtex/hashmap';

const hashMap = new HashMap<any, number>();

hashMap.set({a:34}, 80); // HashMapObject
hashMap.set({a:33}, 81); // HashMapObject

hashMap.size; // 2

hashMap.delete({a:33}); // true
hashMap.delete({b:22}); // false

hashMap.get({a:34}); // 80
hashMap.get({a:44}); // undefined

hashMap.has({a:34}); // true
hashMap.has({a:54}); // false

hashMap.values(); // Iterator {80, 81}
hashMap.keys(); // Iterator {{a:34}, {a:33}}
hashMap.entries(); // Iterator {[{a:34}, 80],[{a:33}, 81]}

hashMap.forEach((value, key, theHashMap) => {
  // do stuff
});

hashMap.clear(); // Removes all key/value pairs

```

#### Javascript
```javascript
import { HashMap } from '@nebtex/hashmap';

const hashMap = new HashMap();

/*
  All the same methods and properties as the typescript example
*/
```