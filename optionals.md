# Optional Parameter vs Optional Chaining
```ts
class A {
  // value have the type number | undefined
  fn(value?: number) {
    console.log(value)
  }
}

const a : A | undefined  | null = new A();

// a have the type number | undefined | null
a?.fn(null);
a?.fn(undefined);
```