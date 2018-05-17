# Use stateless components by default

Use stateless components by default. Extend `React.Component` only when you need features like component state and/or lifecycle methods.

> Why? Make life easier by improving signal to noise ratio.

## Bad 👹

```jsx
import React, { Component } from 'react';

export class Todo extends Component {

  getDeleteButtonString = () => 'x';

  render = () {
    const { todo, deleteTodo } = this.props;

    return (
      <div>
        {todo}
        <span onClick={deleteTodo}>
          {this.getDeleteButtonString()}
        </span>
      </div>
    )
  }
}
```


## Good 👼

```jsx
import React from 'react';

import { getDeleteButtonString } from './utils';

export const Todo = ({ todo, deleteTodo }) => (
  <div>
    {todo}
    <span onClick={deleteTodo}>
      {getDeleteButtonString()}
    </span>
  </div>
)
```
