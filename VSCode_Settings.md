# VSCode_Settings.md

## requirements

- Windows_VSCode.md
- Windows_Claude.md
- Mac_Claude.md

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

## Prettier

### install

[Visual Studio Code] > [左側の Extensions]を押下
[Search Extensions in Marketplace]で以下を検索して[install]を押下

- Prettier - Code formatter

### settings

プロジェクトルートに[.prettierignore], [.prettierrc.json]を保存する

```.prettierignore
*.txt
*.csv

node_modules

normalize.css
package.json
package-lock.json
```

```.prettierrc.json
{
  "semi": false,
  "singleQuote": false,
  "tabWidth": 2,
  "trailingComma": "all"
}
```

## Claude

### install

[Visual Studio Code] > [左側の Extensions]を押下
[Search Extensions in Marketplace]で以下を検索して[install]を押下

- Claude Code for VS Code

### settings

[Visual Studio Code] > [左側の Claude Code]を押下
[Claude.ai Subscription]を押下
[Do you want Code to open the external website?]が表示されたら、[Open]を押下
Websiteで[Claude Code would like to connect to your Claude chat account]が表示されたら、[Authorize]を押下
