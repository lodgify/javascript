# Use generic file names

Use generic file names which describe the contents of the file. Namespace by directory.

> Why? Make life easier by reducing mental burden in navigating the application.

## Bad 👹

```
'-- list
  |-- List.css
  |-- List.js
  |-- List.utils.js
  '-- List.spec.js
```

## Good 👼

```
'-- list
  |-- component.js
  |-- component.spec.js
  |-- index.js
  |-- styles.css
  '-- utils.js
```
