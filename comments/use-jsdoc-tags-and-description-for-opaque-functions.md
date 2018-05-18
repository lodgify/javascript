# Use JSDoc tags and description for opaque functions

If you _have to_ write a function which is difficult to understand by reading, use JSDoc tags and descriptions. Add further comments as required.

> Why? Make life easier by trying as hard as possible to prevent your colleagues' brains exploding.

## Bad 👹

```jsx
const iHateMyColleagues = (x, a, d) => x.reduce((acc, xItem) => acc + xItem * (a/d), 12)
```

## Still bad but better :persevere:

```jsx
/**
 * Returns the sum of the numbers in array x, each multiplied by a/d.
 * The sum is offset by +12.
 * @param  {Number[]} x
 * @param  {Number}   a
 * @param  {Number}   d
 * @return {Number}   
 */
const iHateMyColleagues = (x, a, d) => x.reduce((acc, xItem) => acc + (xItem * (a/d)), 12)
```

## Still bad but we're getting there :confused:

```jsx
/**
 * Returns the sum of the numbers in array x, each multiplied by a/d.
 * The sum is offset by +12.
 * @param  {Number[]} x
 * @param  {Number}   a
 * @param  {Number}   d
 * @return {Number}   
 */
const iHateMyColleagues = (x, a, d) => {
  // evaluate multiplier from a and d, because reasons.
  const multiplier = a/d;
  // iterate over array x to sum its items.
  x.reduce(
    (acc, xItem) => acc + (xItem * multiplier),
    // start the `reduce` iterator at 12, because reasons.
    12
  )
}
```
