# Use ducks for state management logic :duck::duck:

Organise Redux state management logic into 'ducks' modules. This pattern is based on [Erik Rasmussen's proposal](https://github.com/erikras/ducks-modular-redux) with some minor changes to fit Lodgify.

> Why? Reduce the chance of failure by making logic easy to test. Move faster by making logic easy to reuse.


## Good 👼

**/src**

```
modules
'-- todo
  |-- components
  |-- ducks
  | |-- combineReducers.js
  | |-- doneTodos.js
  | |-- doneTodos.spec.js
  | |-- index.js
  | |-- todos.js
  | '-- todos.spec.js
  |
  |-- constants.js
  '-- index.js
```

**.../ducks/doneTodos.js**

Contains everything you need to manage state with Redux i.e.

* the name of the ducks
* initialState
* action types
* reducer
* action creators
* selectors

```jsx
import { MODULE_NAME } from '../constants';

export const DUCKS_NAME = 'doneTodos';

export const initialState = [];

export const ACTION_TYPES = {
  MARK_DONE: `${MODULE_NAME}/${DUCKS_NAME}/MARK_DONE`,
};

export const reducer = (state = initialState, action) => {

  switch (action.type) {
    case ACTION_TYPES.MARK_DONE:
      return [...state, action.id];
    default:
      return state;
  }

};

export const markTodoDone = id => ({
  type: ACTION_TYPES.MARK_DONE,
  id
});

/**
 * @param  {Object} state
 * @return {Number[]}
 */
export const selectDoneTodos = state => state[MODULE_NAME][DUCKS_NAME];
```

**.../ducks/doneTodos.spec.js**

Tests the logic in the corresponding ducks.

There is no need to test action creators, reducers and selectors individually.

Treat each input -> output flow through the ducks as a testable unit.

```jsx
import { configureStore } from 'path/to/store';

import { MODULE_NAME } from '../constants';
import {
  DUCKS_NAME,
  markTodoDone,
  selectDoneTodos,
} from './doneTodos';

describe(`${MODULE_NAME}/ducks/${DUCKS_NAME}`, () => {

  describe('markTodoDone', () => {

    test('should add the id to the array', () => {
        const store = configureStore();
        store.dispatch(markTodoDone(123));
        const state = store.getState();

        expect(selectDoneTodos(state)).toEqual([123]);
    })

  })

})
```

**.../ducks/combineReducers.js**

Combines all the reducers from ducks files in this module.

```jsx
import { combineReducers } from 'redux';

import { reducer as doneTodos } from './doneTodos';
import { reducer as todos } from './todos';

export const reducer = combineReducers({
  doneTodos,
  todos
  // ...and any other reducers from other ducks in this module
});
```

**.../ducks/index.js**

Contains the API for the ducks.

```jsx
export { reducer } from './combineReducers';

export { markTodoDone, selectDoneTodos } from './doneTodos';
```
