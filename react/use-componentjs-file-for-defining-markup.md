# Use `component.js` file for defining markup

Define markup for each React component in a `component.js` file. Namespace the component by directory.

> Why? Make life easier by reducing mental burden in navigating the application.

## Bad 👹

```
modules
'-- todo
  |-- Todo.js
  |-- DeleteButton.js
  '-- utils.js
```

## Good 👼

```
modules
'-- todo
  |-- components
  | |
  | |-- Todo
  | | |-- component.js
  | | '-- index.js
  | |
  | '-- DeleteButton
  |   |-- component.js
  |   '-- index.js
  |
  '-- utils.js
```
