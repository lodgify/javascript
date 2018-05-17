# No logic in `index.js` files

Use `index.js` files only for defining APIs. No logic in `index.js` files.

> Why? Make life easier by reducing mental burden in navigating the application. The developer always knows `index.js` contains only the API

## Bad 👹

**Todo/index.js**
```jsx
import React from 'react';

export const Todo = () => <div>Iron my socks</div>
```


## Good 👼

**Todo/component.js**
```jsx
import React from 'react';

export const Component = () => <div>Iron my socks</div>
```

**Todo/index.js**
```jsx
export { Component } from './component';
```
