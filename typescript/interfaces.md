# Interfaces

## Optional Properties <a id="optional-properties"></a>

Not all properties of an interface may be required.

```typescript
interface SquareConfig {
    color?: string;
    width?: number;
}
```

## Readonly properties <a id="readonly-properties"></a>

```typescript
interface Point {
    readonly x: number;
    readonly y: number;
}
```

### `readonly` vs `const` [\#](https://www.typescriptlang.org/docs/handbook/interfaces.html#readonly-vs-const) <a id="readonly-vs-const"></a>

The easiest way to remember whether to use `readonly` or `const` is to ask whether you’re using it on a variable or a property. Variables use `const` whereas properties use `readonly.`

## Excess Property Checks <a id="excess-property-checks"></a>

 If `SquareConfig` can have `color` and `width` properties with the above types, but could _also_ have any number of other properties, then we could define it like so:

```typescript
interface SquareConfig {
  color?: string;
  width?: number;
  [propName: string]: any;
}
```

## Function Types <a id="function-types"></a>

Interfaces are capable of describing the wide range of shapes that JavaScript objects can take. In addition to describing an object with properties, interfaces are also capable of describing function types.

```typescript
interface SearchFunc {
    (source: string, subString: string): boolean;
}

```

For function types to correctly type check, the names of the parameters do not need to match. We could have, for example, written the above example like this:

```typescript
let mySearch: SearchFunc;
mySearch = function(src: string, sub: string): boolean {
    let result = src.search(sub);
    return result > -1;
}
```

## Implementing an interface

```typescript
interface ClockInterface {
    currentTime: Date;
}

class Clock implements ClockInterface {
    currentTime: Date = new Date();
    constructor(h: number, m: number) { }
}
```

## Extending Interfaces <a id="extending-interfaces"></a>

```typescript
interface Shape {
    color: string;
}

interface PenStroke {
    penWidth: number;
}

interface Square extends Shape, PenStroke {
    sideLength: number;
}

let square = {} as Square;
square.color = "blue";
square.sideLength = 10;
square.penWidth = 5.0
```



