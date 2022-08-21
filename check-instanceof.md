# Check instanceof

```ts
export function createInstanceofPredicate<T>(
  name: string,
  theClass: new (...args: any[]) => T
): (x: any) => x is T {
  const propName = "isMobX" + name;
  theClass.prototype[propName] = true;
  return function (x) {
    return isObject(x) && x[propName] === true;
  } as any;
}
```
