# JavaScript Style Guide

## Linting

- We follow [Airbnb](https://github.com/airbnb/javascript)&rsquo;s JavaScript style guide with [ESlint](https://eslint.org/docs/rules/) integration.
- With **Vue** we use **@vue/cli-plugin-eslint** and **@vue/eslint-config-prettier**.

## Formatting

- We use [Prettier](https://prettier.io/) and we configure it to work well with ESlint.

## Installing dependencies

Step 1: Install **ESlint** + **Prettier**.

```bash
npm install -D eslint prettier
```

Step 2: `eslint-config-airbnb` package has many unwanted dependencies for **Vue**, so install `eslint-config-airbnb-base` instead:

```bash
npx install-peerdeps --dev eslint-config-airbnb-base
```

Note: To use **npx** you need to run **npm 5+**

Step 3: Install: **eslint-config-prettier** to disable formatting for ESLint and **eslint-plugin-prettier** to allow ESLint to show formatting errors.

```bash
npm install -D eslint-config-prettier eslint-plugin-prettier
```

## Configuration

Our default **.eslintrc.js** file:

```js
module.exports = {
  root: true,
  env: {
    browser: true,
    es6: true,
    node: true,
  },
  extends: ['airbnb-base', 'prettier', 'prettier/vue', 'plugin:vue/strongly-recommended'],
  parserOptions: {
    parser: 'babel-eslint',
  },
  plugins: ['vue', 'prettier'],
  rules: {
    'arrow-parens': 0,
    'comma-dangle': 0,
    'function-paren-newline': 0,
    'generator-star-spacing': 0,
    'linebreak-style': 0,
    'import/extensions': 0,
    'import/no-unresolved': 0,
    'import/prefer-default-export': 0,
    'max-len': 0,
    'prefer-template': 0,
    semi: ['error', 'always'],
    'no-console': process.env.NODE_ENV === 'production' ? 'error' : 'off',
    'no-debugger': process.env.NODE_ENV === 'production' ? 'error' : 'off',
    'vue/attributes-order': 0,
    'vue/max-attributes-per-line': 0,
  },
  settings: {
    'import/resolver': {
      webpack: {
        config: 'build/webpack.base.conf.js',
      },
    },
  },
};
```

Our default .prettierrc file:

```json
{
  "bracketSpacing": true,
  "endOfLine": "lf",
  "htmlWhitespaceSensitivity": "ignore",
  "printWidth": 100,
  "semi": true,
  "singleQuote": true,
  "trailingComma": "all",
  "useTabs": false
}
```

In package.json file:

```json
{
  ...
  "scripts": {
      ...
      "lint": "eslint --ext .js,.vue src",
      ...
  },
  ...
}
```

## VS Code

We use [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) and
[ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) extensions.

And make sure to Prettier runs when on save. In **user settings** we set:

```json
"[javascript]": {
    "editor.formatOnSave": true
}
```
