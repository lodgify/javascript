# No JSDoc description for clear functions

Don't write JSDoc descriptions for functions which are clearly written. Use JSDoc tags.

> Why? Make life easier by improving signal to noise ratio. Avoid having to maintain superfluous comments. Incentivise clear functions.

## Bad 👹

```jsx
/**
 * Returns a string id using the id passed into the function.
 * @param  {Number} id - the id
 * @return {String}
 */
const getTodoId = id => `todo-number-${id.toString()}`
```

## Good 👼

```jsx
/**
 * @param  {Number} id
 * @return {String}
 */
const getTodoId = id => `todo-number-${id.toString()}`
```
