<p align="center" style="display: flex; align-items: center; justify-content: center;">
  <img src="https://user-images.githubusercontent.com/61698985/95465266-31704200-097b-11eb-813c-ddc9a0b2f202.png" />
</p>

----

Initialise a React project easily using the anynines React boilerplate.

It comes with preconfigured features like:

- 📦 Webpack
- 🏷️ TypeScript
- ⚛️ React
  - 💄 styled-components
  - 🎨 design-system
- 🌗 Theming
- ✅ Testing
- 🚨 Linter
- 👷 Travis
- 🤡 Mocked API

## 🎉 Quick Start

Generate your new GitHub repositories with this [repository templates](https://github.blog/2019-06-06-generate-new-repositories-with-repository-templates/) or fetch it locally using [degit](https://github.com/Rich-Harris/degit):

```bash
npx degit anynines/anynines-react-boilerplate react-app
cd react-app
```

Install the dependencies...

```bash
yarn install
```

...then start development environment:

```bash
yarn start
```

Navigate to [localhost:9000](http://localhost:9000/). You should see your app running. Edit the `App` component file in `src`, save it, wait that the page reload: you should see your changes.

## 📦 Build the app

We use [webpack](https://webpack.js.org/) to bundle the React app.

You can build it for development:

```bash
yarn start
```

or for production:

```bash
yarn build
```

The generated web app is located in `public`.

## 🏷️ TypeScript

TypeScript's pre-configuration is written in a simple `tsconfig.json`. Modify it as you want.

To easily share global types definition, you can define them in a `.ts` file in `src/types`.

Then export these types in `src/types/index.ts`:

```typescript
export * from './myCreatedTypes'
```

Now you are able to consume them using the `@types` alias:

```javascript
import { CustomType } from '@types'
```

## 🎨 Design system

The boilerplate render for you a [design-system](https://github.com/avarteqgmbh/design_system) instance in `src/theme/ThemeProvider.tsx`. Adjust your options as you want by modifying `DesignSystemInstance` component's props.

Consume the design-system components in the app:

```javascript
import { Button, Icon } from '@anynines/design-system'
```

## 🌗 Theming

You can customize the default theme by modifying the `CUSTOM_THEME` object located in `src/theme/customTheme.ts`.

Consume the `ThemeContext` using the `@theme` alias:

```javascript
import { ThemeContext } from '@theme'

const { theme } = React.useContext(ThemeContext)
```

> Note: The design-system is instanciate and store in `src/designSystemStore.ts`.

## ✅ Testing

[Jest](https://jestjs.io/en/) is already configured with [enzyme](https://enzymejs.github.io/enzyme/). Run the tests using:

```bash
yarn test # run all tests
yarn test:watch # rerun tests after modification
yarn test:coverage # generate tests coverage
```

Add tests by creating a new file `[MyComponent].test.js`. It should be located inside `src`.

## 🚨 Linter

[Eslint](https://eslint.org/) and [stylelint](https://stylelint.io/) are already configured. Check your code by running:

```bash
yarn lint # run linters
yarn lint:js # run eslint linter
yarn lint:css # run stylelint linter
```

## 👷 Travis

The boilerplate provide a [TravisCI](https://travis-ci.com/) basic configuration. On each new commit, it makes sure that the app build, that there are no linter errors and that the tests do not fail:

```bash
yarn build && yarn lint && yarn test
```

## 🤡 Mocked API

The boilerplate run a local mocked API in development environment. You can create `.json` files in `src/mockedApi` and fetch them at `/api/[filename].json`.

You can see it in action by running `yarn start` and go to [localhost:9000/api/users.json](http://localhost:9000/api/users.json). This file is located at `src/mockedApi/users.json`.

You can access these files by using the `@mockedApi` alias:

```javascript
import users from '@mockedApi/users.json'
```


