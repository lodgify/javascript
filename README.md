# Lodgify JavaScript application conventions

An **inexhaustive** definition of Lodgify's conventions for writing JavaScript applications.

## Goals

Each convention seeks to achieve one or more of the following goals, ordered by priority.

#### 😌 Make life easier

Make logic easy to read. Improve signal to noise ratio. Reduce mental burden in understanding.

#### 🔒 Reduce the chance of failure

Make logic easy to test. Choose the tight way (`===`), not the loose way (`==`).

#### 🏃 Move faster

Make logic easy to reuse. Reduce mental burden in writing.

## Conventions

##### Syntax

- [Use Lodgify ESLint config](https://www.npmjs.com/package/eslint-config-lodgify)
- [Use arrow functions by default](syntax/use-arrow-functions-by-default.md)

##### Modules

- [Use modules to organise application logic](modules/use-modules-to-organise-application-logic.md)
- [No default exports](modules/no-default-exports.md)
- [No logic in `index.js` files](modules/no-logic-in-indexjs-files.md)
- [No imports reaching beyond module API](modules/no-imports-reaching-beyond-module-api.md)
- [Use `constants.js` file for defining constants](modules/use-constantsjs-file-for-defining-constants.md)
- [Use `.spec.js` extension for unit test files](modules/use-specjs-extension-for-unit-test-files.md)
- [Use generic file names](modules/use-generic-file-names.md)

##### React

- [No jsx extension](react/no-jsx-extension.md)
- [Use `component.js` file for defining markup](react/use-componentjs-file-for-defining-markup.md)
- [Use stateless components by default](react/use-stateless-components-by-default.md)
- [Use generic component names](react/use-generic-component-names.md)
- [Use `container.js` file for wrapping components](react/use-containerjs-file-for-wrapping-components.md)

##### Redux

- [Use 'ducks' for state management logic :duck::duck:](redux/use-ducks-for-state-management-logic.md)

##### Comments

- [No JSDoc tags or description for boilerplate entities](comments/no-jsdoc-tags-or-description-for-boilerplate-entities.md)
- [No JSDoc tags or description for obvious entities](comments/no-jsdoc-tags-or-description-for-obvious-entities.md)
- [No JSDoc description for clear functions](comments/no-jsdoc-description-for-clear-functions.md)
- [Use JSDoc tags and description for opaque functions](comments/use-jsdoc-tags-and-description-for-opaque-functions.md)

## ☝️ Be warned

This is consciously **inexhaustive**.

If something isn't covered here, fall back to a sensible convention in [AirBnB](https://github.com/airbnb/javascript) or [make a contribution](#contributions). When another convention conflicts with a convention here, follow the one here.

## Contributions

Use the [convention template](CONVENTION_TEMPLATE.md) and open a PR into master branch.
