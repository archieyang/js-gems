# Mapped Types

```ts
interface A {
  a: number;
  b: string;
  c: boolean;
}

type B = { [k in keyof A]: boolean };

// Property 'c' is missing in type '{ a: true; b: true; }' but required in type 'B'.
const b: B = { a: true, b: true };
```
