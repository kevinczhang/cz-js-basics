# Iterators and Generators

## Iterables <a id="iterables"></a>

 An object is deemed iterable if it has an implementation for the [`Symbol.iterator`](https://www.typescriptlang.org/docs/handbook/symbols.html#symboliterator) property. Some built-in types like `Array`, `Map`, `Set`, `String`, `Int32Array`, `Uint32Array`, etc. have their `Symbol.iterator` property already implemented. `Symbol.iterator` function on an object is responsible for returning the list of values to iterate on.

### `for..of` vs. `for..in` statements [\#](https://www.typescriptlang.org/docs/handbook/iterators-and-generators.html#forof-vs-forin-statements)

Both `for..of` and `for..in` statements iterate over lists; the values iterated on are different though, `for..in` returns a list of _keys_ on the object being iterated, whereas `for..of` returns a list of _values_ of the numeric properties of the object being iterated.

```typescript
let list = [4, 5, 6];

for (let i in list) {
    console.log(i); // "0", "1", "2",
}

for (let i of list) {
    console.log(i); // "4", "5", "6"
}
```



