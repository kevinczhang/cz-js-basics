# Basic Types

```typescript
// Boolean
let isDone: boolean = false;

// Number
let decimal: number = 6;
let hex: number = 0xf00d;
let binary: number = 0b1010;
let octal: number = 0o744;

// String
let color: string = "blue";
color = 'red';

let fullName: string = `Bob Bobbington`;
let age: number = 37;
let sentence: string = `Hello, my name is ${ fullName }. 
    I'll be ${ age + 1 } years old next month.`;

// Array
let list: number[] = [1, 2, 3];
let list: Array<number> = [1, 2, 3];
```

## Tuple

Tuple types allow you to express an array with a fixed number of elements whose types are known, but need not be the same.

```typescript
// Tuple
let x: [string, number];
// Initialize it
x = ["hello", 10]; // OK
// Initialize it incorrectly
x = [10, "hello"]; // Error
```

## Enum

 A helpful addition to the standard set of datatypes from JavaScript is the `enum`. As in languages like C\#, an enum is a way of giving more friendly names to sets of numeric values.

```typescript
// Enum
enum Color {Red, Green, Blue}
let c: Color = Color.Green;
```

 By default, enums begin numbering their members starting at `0`. You can change this by manually setting the value of one of its members. For example, we can start the previous example at `1` instead of `0`:

```typescript
enum Color {Red = 1, Green = 2, Blue = 4}
let c: Color = Color.Green;
```

## Any

 The `any` type is a powerful way to work with existing JavaScript, allowing you to gradually opt-in and opt-out of type checking during compilation. You might expect `Object` to play a similar role, as it does in other languages. However, variables of type `Object` only allow you to assign any value to them. You can’t call arbitrary methods on them, even ones that actually exist:

```typescript
let notSure: any = 4;
notSure.ifItExists(); // okay, ifItExists might exist at runtime
notSure.toFixed(); // okay, toFixed exists (but the compiler doesn't check)

let prettySure: Object = 4;
prettySure.toFixed(); // Error: Property 'toFixed' doesn't exist on type 'Object'.
```

## Type assertions <a id="type-assertions"></a>

 _Type assertions_ are a way to tell the compiler “trust me, I know what I’m doing.” A type assertion is like a type cast in other languages, but performs no special checking or restructuring of data. It has no runtime impact, and is used purely by the compiler. 

```typescript
let someValue: any = "this is a string";

let strLength: number = (someValue as string).length;
```



