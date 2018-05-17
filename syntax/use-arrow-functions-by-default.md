# Use arrow functions by default

Use arrow functions by default. Use other function syntax only when you need specific behaviour [like binding `this`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this).

> Why? Make life easier by improving signal to noise ratio.

## Bad 👹

```jsx
const getOne = function() { return 1 };

function getOne() { return 1 };
```


## Good 👼

```jsx
const getOne = () => 1;
```
