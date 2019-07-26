# Generics

```typescript
function identity<T>(arg: T): T {
    return arg;
}

let myIdentity: <T>(arg: T) => T = identity;
```

## Generic Classes <a id="generic-classes"></a>

```typescript
class GenericNumber<T> {
    zeroValue: T;
    add: (x: T, y: T) => T;
}

let myGenericNumber = new GenericNumber<number>();
myGenericNumber.zeroValue = 0;
myGenericNumber.add = function(x, y) { return x + y; };

let stringNumeric = new GenericNumber<string>();
stringNumeric.zeroValue = "";
stringNumeric.add = function(x, y) { return x + y; };
```

## Generic Constraints <a id="generic-constraints"></a>

```typescript
interface Lengthwise {
    length: number;
}

function loggingIdentity<T extends Lengthwise>(arg: T): T {
    console.log(arg.length);  
    // Now we know it has a .length property, so no more error
    return arg;
}
```

### Using Type Parameters in Generic Constraints <a id="using-type-parameters-in-generic-constraints"></a>

```typescript
function getProperty<T, K extends keyof T>(obj: T, key: K) {
    return obj[key];
}

let x = { a: 1, b: 2, c: 3, d: 4 };

getProperty(x, "a"); // okay
getProperty(x, "m"); 
// error: Argument of type 'm' isn't assignable to 'a' | 'b' | 'c' | 'd'.
```

