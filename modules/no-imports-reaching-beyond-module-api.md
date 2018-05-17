# No imports reaching beyond module API

Import only from the API defined by a module. Do not reach into the module.

> Why? Reduce the chance of failure by avoiding circular dependencies. Move faster by creating decoupled, easy to reuse modules.

## Bad 👹

```jsx
import { Todo } from 'modules/todo/components/Todo/component';
```


## Good 👼

```jsx
import { Todo } from 'modules/todo';
```
