Implied Scopes

```js
function fn(p0  = 0, defaultP0 = () => p0) {
  var p0 = 3;
  console.log(p0); // 3
  console.log(defaultP0()); // 0
}

fn();

const f1 = function functionName() {
  // no duplicate declaration error
  let functionName = 'something else';
}
```