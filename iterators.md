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
