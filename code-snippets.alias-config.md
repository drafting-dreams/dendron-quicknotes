---
id: HpUlgKdaV8pN9Tam0cgPg
title: Alias Config
desc: ''
updated: 1639846978613
created: 1639843806504
---

Create aliases to `import` or `require` certain modules more easily. For example, to alias a bunch of commonly used `src/` folders

```js
const path = require('path')

module.exports = {
  //...
  resolve: {
    alias: {
      '@': path.resolve(__dirname, 'src/'),
    },
  },
}
```

However, vscode doesn't recognize this alias. The redirect function wouldn't work if only webpack is configed with alias. Thus, we also need to set `compilerOptions` in `tsconfig.json/jsconfig.json`

```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"]
    }
  }
}
```

Additionally, if you're also using `eslint`, it also need to be configed. Otherwise it will prompt error that "can't resolve the module". To tackle this, install these two packages `eslint-plugin-import` and `eslint-import-resolver-alias`. And add the following config into the `.eslintrc`

```js
module.exports = {
  settings: {
    'import/resolver': {
      alias: {
        map: [['@', './src']],
        extensions: ['.ts', '.js', '.jsx', '.json'],
      },
    },
  },
}
```

At last, a little hint about `create-react-app`, everytime it runs, it delete the `compilerOptions` inside `tsconfig.js`. A way to get around this is to create another `tsconfig.path.js` and let `tsconfig.js` extends it.
