# Sparse Array

```js
function isDense(array) {
  for (let index = 0; index < array.length; index++) {
    if (!(index in array)) {
      return false;
    }
  }
  return true;
}

const denseArray = [0, 1, 2, 3];
const sparseArray = [];
sparseArray[10001] = 9322;

// true
console.log(isDense(denseArray));

// false
console.log(isDense(sparseArray));
```
