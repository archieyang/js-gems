# Object changeable

```ts
/**
 * Prevents the modification of attributes of existing properties, and prevents the addition of new properties.
 * @param o Object on which to lock the attributes.
 */
seal<T>(o: T): T;

/**
 * Prevents the modification of existing property attributes and values, and prevents the addition of new properties.
 * @param a Object on which to lock the attributes.
 */
freeze<T>(a: T[]): readonly T[];

/**
 * Prevents the addition of new properties to an object.
 * @param o Object to make non-extensible.
 */
preventExtensions<T>(o: T): T;
```
