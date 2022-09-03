# Function Declaration vs Function Expression
```js
class A {
  a = "hi variable";
  
  f0 = function() {};
  
  f1 = ()=> {}
  
  f2(){};
}

const a = new A();

console.log(a.__proto__.a); // undefined, variable declaration
console.log(a.__proto__.f0); // undefined, function expression
console.log(a.__proto__.f1); // undefined, function expression
console.log(a.__proto__.f2); // f2() { }, function declaration defined on the prototype

```