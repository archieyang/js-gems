# Iterators

## Iterate over an array with indices

```js
var arr = [10, 20, 30];

for (let [idx, val] of arr.entries()) {
  console.log(`[${idx}]: ${val}`);
}
// [0]: 10
// [1]: 20
// [2]: 30
```

## for...in vs for...of

```ts
let arr = ["Alice", "Bob", "Catherine"];

arr.someone = "Dan";

// Prints 0, 1, 2 and someone
for (let key in arr) {
  console.log(key);
}

// Prints Alice, Bob and Catherine
for (let value of arr) {
  console.log(value);
}
```
