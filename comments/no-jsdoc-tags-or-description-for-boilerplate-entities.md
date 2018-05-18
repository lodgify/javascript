# No JSDoc tags or description for boilerplate entities

Don't document boilerplate entities which are used when consuming libraries. The library creator documents these better.

> Why? Make life easier by improving signal to noise ratio.

## Bad 👹

```jsx
import { connect } from 'react-redux';

...

/**
 * Maps application state to props
 * @param  {Object} state - application state
 * @return {Object}       - props
 */
const mapStateToProps = state => ({
    todos: selectTodos(state),
});

export const Container = connect(mapStateToProps)(Component);
```

## Good 👼

`mapStateToProps` is [well documented by `react-redux`](https://github.com/reduxjs/react-redux/blob/master/docs/api.md#arguments).

```jsx
import { connect } from 'react-redux';

...

const mapStateToProps = state => ({
    todos: selectTodos(state),
});

export const Container = connect(mapStateToProps)(Component);
```
