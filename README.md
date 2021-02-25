### Prettier(https://prettier.io)

> 安装

```
yarn add prettier --dev
```

> config file

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

format options：https://prettier.io/docs/en/options.html

> ignore file

```
// .prettierignore

node_modules
...
```

> manual（手动） format

```
// format all files
prettier --write .

// format a certain（某一） directory
prettier --write src/

// format a certain file
prettier --write src/index.js

// format all .js in a dirctory
prettier --write src/**/*.js
```

> cmd + s （保存时自动格式化）

1. Webstorm > Preferences > Tools > File Watchers

2. `+` > Prettier


### prettier && husky && lint-staged

*注意：* 使用 `husky` 之前，项目必须 `git init` 过。

*husky：*(https://typicode.github.io/husky/#/)

*lint-staged：*(https://github.com/okonet/lint-staged#readme)

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

*eslint-plugin-prettier：*(https://github.com/prettier/eslint-plugin-prettier#readme)

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
