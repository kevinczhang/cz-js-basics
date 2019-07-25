# Variable Declarations

## Destructuring <a id="destructuring"></a>

### Array destructuring <a id="array-destructuring"></a>

```typescript
let input = [1, 2];
let [first, second] = input;

// swap variables
[first, second] = [second, first];

let [first, ...rest] = [1, 2, 3, 4];
console.log(first); // outputs 1
console.log(rest); // outputs [ 2, 3, 4 ]

let [, second, , fourth] = [1, 2, 3, 4];
console.log(second); // outputs 2
console.log(fourth); // outputs 4
```

### Tuple destructuring <a id="tuple-destructuring"></a>

Tuples may be destructured like arrays; the destructuring variables get the types of the corresponding tuple elements:

```typescript
let tuple: [number, string, boolean] = [7, "hello", true];
let [a, b, c] = tuple; // a: number, b: string, c: boolean

let [a, ...bc] = tuple; // bc: [string, boolean]
let [a, b, c, ...d] = tuple; // d: [], the empty tuple

let [a] = tuple; // a: number
let [, b] = tuple; // b: string
```

### Object destructuring <a id="object-destructuring"></a>

```typescript
let o = {
    a: "foo",
    b: 12,
    c: "bar"
};
let { a, b } = o;
```

 You can create a variable for the remaining items in an object using the syntax `...`:

```typescript
let { a, ...passthrough } = o;
let total = passthrough.b + passthrough.c.length;
```

#### Property renaming <a id="property-renaming"></a>

```typescript
let { a: newName1, b: newName2 } = o;
```

## Spread

The spread operator is the opposite of destructuring. It allows you to spread an array into another array, or an object into another object.

```typescript
let first = [1, 2];
let second = [3, 4];
let bothPlus = [0, ...first, ...second, 5];
```

You can also spread objects

```typescript
let defaults = { food: "spicy", price: "$$", ambiance: "noisy" };
let search = { ...defaults, food: "rich" };
```

 Object spread also has a couple of other surprising limits. First, it only includes an objects’ [own, enumerable properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties). Basically, that means you lose methods when you spread instances of an object:

Second, the Typescript compiler doesn’t allow spreads of type parameters from generic functions. That feature is expected in future versions of the language.

