# No default exports

Use named exports only. No default exports. ESLint rule [`no-default-exports`](https://github.com/benmosher/eslint-plugin-import/blob/master/docs/rules/no-default-export.md).

> Why? Reduce both mental burden and the chance of failure by enforcing consistent naming across files.

## Bad 👹

```jsx
const someEntity = '1';

export default someEntity;
```

## Good 👼

```jsx
export const someEntity = '1';
```
