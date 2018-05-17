# Use `constants.js` file for defining constants

Don't mix logic with constants. Define constants in a discrete `constants.js` file.

> Why? Make life easier by reducing mental burden in navigating the application. Reduce the chance of failure by defining and reusing constant values.

## Bad 👹

**api-client.js**

```jsx
fetch('//api.com/todos');
```

or

**api-client.js**

```jsx
const API_URI = '//api.com/todos';

fetch(API_URI);
```


## Good 👼

**api-client.js**

```jsx
import { API_URI } from './constants';

fetch(API_URI);
```

**constants.js**

```jsx
export const API_URI = '//api.com/todos';
```
