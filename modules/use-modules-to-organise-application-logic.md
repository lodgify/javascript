# Use modules to organise application logic

Organise applications into functional modules. Don't organise by logic type.

See [this post by Jack Hsu](https://jaysoo.ca/2016/02/28/applying-code-organization-rules-to-concrete-redux-code/#module-index-and-constants
).

> Why? Move faster by making logic easy to reuse, remove and replace.

## Bad 👹

```
src
|
|-- components
| |-- list-component.js
| |-- login-component.js
| '-- todo-component.js
|
|-- constants
| |-- list-constants.js
| |-- login-constants.js
| '-- todo-constants.js
|
'-- utils
  |-- list-utils.js
  |-- login-utils.js
  '-- todo-utils.js
```

## Good 👼

```
src
|
'-- modules
  |
  |-- list
  | |-- component.js
  | |-- constants.js
  | '-- utils.js
  |
  |-- login
  | |-- component.js
  | |-- constants.js
  | '-- utils.js
  |
  '-- todo
    |-- component.js
    |-- constants.js
    '-- utils.js
```
