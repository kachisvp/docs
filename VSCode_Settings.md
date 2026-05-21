# VSCode_Settings.md

## requirements

- Windows_VSCode.md

## extensions

[Visual Studio Code] > [左側の Extensions]を押下
[Search Extensions in Marketplace]で以下を検索して[install]を押下

- Prettier - Code formatter

## settings

[Visual Studio Code] > [File] > [Preferences] > [Settings]を押下
右上の[Open Settings (JSON)]を押下
右上の[Open Modal Editor in Main Window]を押下
以下の設定が存在しない場合、追記する

```
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "editor.renderWhitespace": "all",
  "git.autofetch": true,
  "prettier.configPath": ".prettier.json",
  "prettier.requireConfig": true,
  "window.newWindowDimensions": "inherit",
  "[json]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true,
  },
```

### Prettier

プロジェクトルートに[.prettier.json], [.prettierignore]を保存する

```.prettier.json
{
  "semi": false,
  "singleQuote": false,
  "tabWidth": 2,
  "trailingComma": "es6"
}
```

```.prettierignore
*.txt
*.csv

node_modules

normalize.css
package.json
package-lock.json
```
