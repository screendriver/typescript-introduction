# TypeScript introduction

An introduction to the [TypeScript](https://www.typescriptlang.org) language, a
superset of JavaScript that compiles to plain JavaScript.

---

## Basic Types

---

```ts
const isDone: boolean = false;
const decimal: number = 6;
const color: string = 'blue';
const list: number[] = [1, 2, 3];
// Like an array but with fixed number of elements
const tuple: [string, number] = ['hello', 10];
```

---

## Enums

---

### Numeric enums

```ts
enum Color {
  Red,
  Green,
  Blue,
}
const c: Color = Color.Green; // 1
```

---

```ts
// You can also go from a numeric value to the
// name of that value
enum Color {
  Red = 1,
  Green,
  Blue,
}
const colorName: string = Color[2];

alert(colorName); // Displays 'Green' as its value is 2 above
```

---

### String enums

```ts
enum Direction {
  Up = 'UP',
  Down = 'DOWN',
  Left = 'LEFT',
  Right = 'RIGHT',
}
```

---

### Const enums

Enums are real objects that exist at runtime! They get a reverse mapping from
enum values to enum names.

```ts
enum Enum {
  A,
}
const a = Enum.A;
const nameOfA = Enum[a]; // "A"
```

TypeScript generates an object that stores both forward (name -> value) and
reverse (value -> name) mappings.

---

If you don't need that and to reduce the amount
of generated code you can use `const enums` instead.

```ts
const enum Enum {
  A,
  B,
}
```

Unlike regular enums they are **completely removed** during compilation.

```ts
const foo = [Enum.A, Enum.B];
```

```js
const foo = [0 /* A */, 1 /* B */];
```
