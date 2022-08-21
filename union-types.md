# extends and Union Types

```ts
interface A {}
interface B {}
interface C {}

type UnionAB = A | B;
type UnionABC = A | B | C;

type Result = UnionAB extends UnionABC ? boolean : number;
// Result is boolean
```
