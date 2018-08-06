# JavaScript

## Linting

- We follow [Airbnb](https://github.com/airbnb/javascript)&rsquo;s JavaScript style guide with [ESlint](https://eslint.org/docs/rules/) integration.
- In **Vue** we use **@vue/cli-plugin-eslint** and **@vue/eslint-config-prettier**.

## Formatting

- We use [Prettier](https://prettier.io/) and we configure it for works well with ESlint.

## Installing dependencies

First we install **ESlint** + **Prettier**.

```bash
npm install -D eslint prettier
```

Then we install **Airbnb config**. Airbnb config has own dependencies like:

```bash
eslint-config-airbnb eslint eslint-plugin-jsx-a11y
eslint-plugin-import eslint-plugin-react
```

instead of installing all these manually. We use:

```bash
npx install-peerdeps --dev eslint-config-airbnb
```

(For using **npx** you need to use **npm 5+** )

After we install: **eslint-config-prettier** for disabling formatting for ESLint and **eslint-plugin-prettier** for allowing ESLint to show formatting
errors.

```bash
npm install -D eslint-config-prettier eslint-plugin-prettier
```

## Configuration

Our default **.eslintrc** file:

```json
{
  "extends": ["airbnb", "prettier"],
  "plugins": ["prettier"],
  "parserOptions": {
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "env": {
    "browser": true,
    "es6": true,
    "node": true
  },
  "rules": {
    "prettier/prettier": "error"
  }
}
```

Our default .prettierrc file:

```json
{
  "printWidth": 100,
  "singleQuote": true,
  "trailingComma": "all"
}
```

In package.json file:

```json
{
  ...
  "scripts": {
      "lint": "eslint ."
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
