---
description: Methods to manipulate arrays
---

# Array

### `_.compact(array)`

 Creates an array with all falsey values removed. The values `false`, `null`, `0`, `""`, `undefined`, and `NaN` are falsey.

```javascript
_.compact([0, 1, false, 2, '', 3]);
// => [1, 2, 3]
```

### `_.concat(array, [values])`

 Creates a new array concatenating `array` with any additional arrays and/or values.

```javascript
var array = [1];
var other = _.concat(array, 2, [3], [[4]]); 
console.log(other);
// => [1, 2, 3, [4]] 
console.log(array);
// => [1]
```

### `_.drop(array, [n=1])`

 Creates a slice of `array` with `n` elements dropped from the beginning.

```javascript
_.drop([1, 2, 3]);
// => [2, 3] 
_.drop([1, 2, 3], 2);
// => [3] 
_.drop([1, 2, 3], 5);
// => [] 
_.drop([1, 2, 3], 0);
// => [1, 2, 3]
```

### `_.fill(array, value, [start=0], [end=array.length])`

 Fills elements of `array` with `value` from `start` up to, but not including, `end`.

```javascript
var array = [1, 2, 3];
 
_.fill(array, 'a');
console.log(array);
// => ['a', 'a', 'a']
 
_.fill(Array(3), 2);
// => [2, 2, 2]
 
_.fill([4, 6, 8, 10], '*', 1, 3);
// => [4, '*', '*', 10]
```

### `_.findIndex(array, [predicate=_.identity], [fromIndex=0])`

 This method is like [`_.find`](https://lodash.com/docs/4.17.15#find) except that it returns the index of the first element `predicate` returns truthy for instead of the element itself.

```javascript
var users = [
  { 'user': 'barney',  'active': false },
  { 'user': 'fred',    'active': false },
  { 'user': 'pebbles', 'active': true }
];
 
_.findIndex(users, function(o) { return o.user == 'barney'; });
// => 0
 
// The `_.matches` iteratee shorthand.
_.findIndex(users, { 'user': 'fred', 'active': false });
// => 1
 
// The `_.matchesProperty` iteratee shorthand.
_.findIndex(users, ['active', false]);
// => 0
 
// The `_.property` iteratee shorthand.
_.findIndex(users, 'active');
// => 2
```

### `_.flatten(array)`

 Flattens `array` a single level deep.

```javascript
_.flatten([1, [2, [3, [4]], 5]]);
// => [1, 2, [3, [4]], 5]
```

#### `_.flattenDeep(array)` <a id="flattenDeep"></a>

 Recursively flattens `array`.

```javascript
_.flattenDeep([1, [2, [3, [4]], 5]]);
// => [1, 2, 3, 4, 5]
```

#### `_.fromPairs(pairs)` <a id="fromPairs"></a>

 The inverse of [`_.toPairs`](https://lodash.com/docs/4.17.15#toPairs); this method returns an object composed from key-value `pairs`.

```javascript
_.fromPairs([['a', 1], ['b', 2]]);
// => { 'a': 1, 'b': 2 }
```

#### `_.join(array, [separator=','])` <a id="join"></a>

 Converts all elements in `array` into a string separated by `separator`.

```javascript
_.join(['a', 'b', 'c'], '~');
// => 'a~b~c'
```

#### `_.pull(array, [values])` <a id="pull"></a>

 Removes all given values from `array` using [`SameValueZero`](http://ecma-international.org/ecma-262/7.0/#sec-samevaluezero) for equality comparisons.

```javascript
var array = ['a', 'b', 'c', 'a', 'b', 'c'];
 
_.pull(array, 'a', 'c');
console.log(array);
// => ['b', 'b']
```

#### `_.pullAll(array, values)` <a id="pullAll"></a>

 This method is like [`_.pull`](https://lodash.com/docs/4.17.15#pull) except that it accepts an array of values to remove.

```javascript
var array = ['a', 'b', 'c', 'a', 'b', 'c'];
 
_.pullAll(array, ['a', 'c']);
console.log(array);
// => ['b', 'b']
```

#### `_.remove(array, [predicate=_.identity])` <a id="remove"></a>

 Removes all elements from `array` that `predicate` returns truthy for and returns an array of the removed elements. The predicate is invoked with three arguments: _\(value, index, array\)_.

```javascript
var array = [1, 2, 3, 4];
var evens = _.remove(array, function(n) {
  return n % 2 == 0;
});
 
console.log(array);
// => [1, 3]
 
console.log(evens);
// => [2, 4]
```

#### `_.reverse(array)` <a id="reverse"></a>

 Reverses `array` so that the first element becomes the last, the second element becomes the second to last, and so on.

```javascript
var array = [1, 2, 3];
 
_.reverse(array);
// => [3, 2, 1]
 
console.log(array);
// => [3, 2, 1]
```

#### `_.slice(array, [start=0], [end=array.length])` <a id="slice"></a>

 Creates a slice of `array` from `start` up to, but not including, `end`.

#### `_.take(array, [n=1])` <a id="take"></a>

 Creates a slice of `array` with `n` elements taken from the beginning.

```javascript
_.take([1, 2, 3]);
// => [1]
 
_.take([1, 2, 3], 2);
// => [1, 2]
 
_.take([1, 2, 3], 5);
// => [1, 2, 3]
 
_.take([1, 2, 3], 0);
// => []
```

#### `_.takeRight(array, [n=1])` <a id="takeRight"></a>

 Creates a slice of `array` with `n` elements taken from the end.

```javascript
_.takeRight([1, 2, 3]);
// => [3]
 
_.takeRight([1, 2, 3], 2);
// => [2, 3]
 
_.takeRight([1, 2, 3], 5);
// => [1, 2, 3]
 
_.takeRight([1, 2, 3], 0);
// => []
```

#### `_.union([arrays])` <a id="union"></a>

 Creates an array of unique values, in order, from all given arrays using [`SameValueZero`](http://ecma-international.org/ecma-262/7.0/#sec-samevaluezero) for equality comparisons.

```javascript
_.union([2], [1, 2]);
// => [2, 1]
```

#### `_.uniq(array)` <a id="uniq"></a>

 Creates a duplicate-free version of an array, using [`SameValueZero`](http://ecma-international.org/ecma-262/7.0/#sec-samevaluezero) for equality comparisons, in which only the first occurrence of each element is kept. The order of result values is determined by the order they occur in the array.

```javascript
_.uniq([2, 1, 2]);
// => [2, 1]
```

#### `_.unzip(array)` <a id="unzip"></a>

 This method is like [`_.zip`](https://lodash.com/docs/4.17.15#zip) except that it accepts an array of grouped elements and creates an array regrouping the elements to their pre-zip configuration.

```javascript
var zipped = _.zip(['a', 'b'], [1, 2], [true, false]);
// => [['a', 1, true], ['b', 2, false]]
 
_.unzip(zipped);
// => [['a', 'b'], [1, 2], [true, false]]
```

#### `_.xor([arrays])` <a id="xor"></a>

 Creates an array of unique values that is the [symmetric difference](https://en.wikipedia.org/wiki/Symmetric_difference) of the given arrays. The order of result values is determined by the order they occur in the arrays.

```javascript
_.xor([2, 1], [2, 3]);
// => [1, 3]
```



