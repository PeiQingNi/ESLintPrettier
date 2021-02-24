### [Prettier](https://prettier.io)

> 安装

```
yarn add prettier --dev
```

> 配置文件

```
// .prettierrc.json

{
  "singleQuote": true
  ...
}

// .prettierrc.js
module.exports = {
  singleQuote: true
  ...
}
```

> ignore

```
// .prettierignore

node_modules
...
```

> cmd + s

1. Webstorm > Preferences > Tools > File Watchers

2. `+` > Prettier


### prettier && [husky](https://typicode.github.io/husky/#/) && [lint-staged](https://github.com/okonet/lint-staged#readme)

*注意：* 使用 `husky` 之前，项目必须 `git init` 过。

> 安装

```
// 注意：使用5.0.0之前的版本
yarn add husky@4.3.8 --dev

yarn add lint-staged --dev
```

> package.json

```
"husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "src/**/*.{js,jsx,css,json}": [
      "prettier --write"
    ]
  }
```


### prettier && husky && lint-staged && eslint

> 安装

```
yarn add eslint --dev
```

> 生成配置文件

```
eslint --init
```

> 配置 prettier

[eslint-plugin-prettier](https://github.com/prettier/eslint-plugin-prettier#readme)

```
yarn add eslint-plugin-prettier --dev

yarn add eslint-config-prettier --dev

// .eslintrc.json
{
  extends: [
    ...
    "plugin:prettier/recommended"
  ]
}
```

> package.json

```
"husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "src/**/*.{js,jsx,css,json}": [
      "prettier --write"
      "eslint --fix"
    ]
  }
```
