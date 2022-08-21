# Reflect.ownKeys()

```ts
class Animal {
  name = "Dod";

  bark = function () {
    console.log("bark");
  };

  run() {
    console.log("run");
  }
}

const a = new Animal();
console.log(JSON.stringify(Reflect.ownKeys(a)));
console.log(JSON.stringify(Reflect.ownKeys(a.__proto__)));
```
