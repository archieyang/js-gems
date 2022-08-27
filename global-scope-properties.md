# Global Scope Properties

```ts
var aVar = 'var';
let aLet = 'let';

function fn(){}

// 'var'
console.log(this['aVar']);

// undefined
console.log(this['aLet']);

// function fn() { } 
console.log(this['fn']);
```