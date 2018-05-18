# No JSDoc tags or description for obvious entities

Don't document obvious entities.

> Why? Make life easier by improving signal to noise ratio. Avoid having to maintain superfluous comments. Incentivise semantic naming of entities.

## Bad 👹

```jsx
// The name of the module
export const MODULE_NAME = 'todos';
```

```jsx
/**
 * The name of the module
 * @type {String}
 */
export const MODULE_NAME = 'todos';
```

```jsx
/**
 * @type {String}
 */
export const MODULE_NAME = 'todos';
```

## Good 👼

```jsx
export const MODULE_NAME = 'todos';
```
