# Use generic component names

Use generic names for React components. Define semantic component names at the API level and using `displayName`.

> Why? Make life easier by improving signal to noise ratio. Move faster by making logic easier to copy and reuse.

## Bad 👹

**Todo/component.js**

```jsx
export const TodoComponent = () => <div>Iron my socks</div>;
```

**Todo/container.js**

```jsx
import { TodoComponent } from './component';

...

export const TodoContainer = connect(mapStateToProps)(TodoComponent);
```

**Todo/index.js**

```jsx
export { TodoContainer as Todo } from './container';
```

## Good 👼

**Todo/component.js**

```jsx
export const Component = () => <div>Iron my socks</div>;

Component.displayName = 'Todo';
```

**Todo/container.js**

```jsx
import { Component } from './component';

...

export const Container = connect(mapStateToProps)(Component);
```

**Todo/index.js**

```jsx
export { Container as Todo } from './container';
```
