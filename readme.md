# @alwaysai/eslint-config

ESLint configurations for alwaysAI projects

## Note
We haven't actually used this for anything yet. We published the package to npm though, which is irreversible, and we might still use it for TypeScript or for JavaScript. So we'll keep this repo around too!\

## Usage
Install this package and the `eslint` command-line tool:

```
npm install --save --save-dev @alwaysai/eslint-config eslint
```

Create a file `.eslintrc.json` at the root of your project with contents:

```json
{
  "extends": [
    "@alwaysai/eslint-config"
  ]
}
```

Add these lines to your `package.json`'s "scripts" field:
```
  "lint": "eslint --ext .ts,.tsx <directory>",
  "lint:fix": "npm run lint -- --fix",
```

where `<directory>` is the subdirectory of your project containing the source code that you want to lint. Finally add `&& npm run lint` to your package's "test" script to make sure you enforce the lint rules! We recommend setting up your editor to automatically fix lint errors on save. That way the linter mostly stays out of your way and just does the right thing. In Visual Studio Code, [this plugin](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) works great.

## Rules
This package's rules extend those espoused by [by AirBnB](https://github.com/airbnb/javascript), consumed as [eslint-config-airbnb](https://www.npmjs.com/package/eslint-config-airbnb). Those rules are mostly concerned with syntax. For code formatting, this package uses [`eslint-config-prettier`](https://github.com/prettier/eslint-config-prettier), which disables all rules that are unnecessary or might conflict with [Prettier](https://prettier.io/). Instead of calling `prettier` directly, this package employs [`eslint-plugin-prettier`](https://github.com/prettier/eslint-plugin-prettier), which "runs Prettier as a ESLint rule and reports differences as individual ESLint issues".

## Related
- [@alwaysai/tsconfig](https://github.com/alwaysai/tsconfig): TypeScript configurations for alwaysAI projects

## License
MIT © [alwaysAI, Inc.](https://alwaysai.co)
