# Use `container.js` file for wrapping components

Keep component-wrapping logic in a separate file to markup. Use the filename `container.js`.

> Why? Make life easier by making logic easier to read and reducing the mental burden in navigating the application.

## Bad 👹

**Todo/component.js**

```jsx
...

const Component = ({ clothingItem }) => <div>Iron my {clothingItem}</div>;

const mapStateToProps = state => ({
  clothingItem: selectClothingItem(state)
});

export const Container = connect(mapStateToProps)(Component);
```

or

```jsx
...

const mapStateToProps = state => ({
  clothingItem: selectClothingItem(state)
});

@connect(mapStateToProps)
export class Component extends React.Component {

  ...

  render = () => <div>Iron my {this.props.clothingItem}</div>;

}
```


## Good 👼

**Todo/component.js**

```jsx
...

export const Component = ({ clothingItem }) => <div>Iron my {clothingItem}</div>;
```

**Todo/container.js**

```jsx
...

import { Component } from './component';

const mapStateToProps = state => ({
  clothingItem: selectClothingItem(state)
});

export const Container = connect(mapStateToProps)(Component);
```
