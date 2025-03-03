# eslint-plugin-no-empty

An ESLint plugin to enforce using EMPTY_STRING constant instead of empty string literals.

## Installation

You'll first need to install [ESLint](https://eslint.org/):

```bash
npm i eslint --save-dev
```

Next, install `@vovapuchkov/eslint-plugin-no-empty`:

```bash
npm install @vovapuchkov/eslint-plugin-no-empty --save-dev
```

## Usage

Add `no-empty` to the plugins section of your `.eslintrc` configuration file:

```json
{
  "plugins": ["@vovapuchkov/no-empty"]
}
```

Then configure the rules you want to use under the rules section:

```json
{
  "rules": {
    "@vovapuchkov/no-empty/no-empty-strings": "error"
  }
}
```

## Rules

### no-empty-strings

This rule enforces that empty string literals (`""`) are not used directly in the code. Instead, it requires using the `EMPTY_STRING` constant from `src/Utils/consts`.

Example of incorrect code:

```js
const emptyName = "";
```

Example of correct code:

```js
import { EMPTY_STRING } from 'src/Utils/consts';

const emptyName = EMPTY_STRING;
```

This rule is fixable and will automatically add the import and replace empty string literals with `EMPTY_STRING`.

## License

MIT 