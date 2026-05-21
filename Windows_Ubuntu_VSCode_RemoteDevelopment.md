# Windows_Ubuntu_VSCode_RemoteDevelopment.md

## requirements

- Windows_VSCode.md
- VSCode_Settings.md
- Windows_Ubuntu.md

## extensions

[Visual Studio Code] > [左側の Extensions]を押下
[Search Extensions in Marketplace]で以下を検索して[install]を押下

- Remote Development

## settings

[Visual Studio Code] > [左側の Remote Explorer]を押下
[WSL TARGET] > [Ubuntu] > [右側の Connect in Current Window]を押下
[左側のExplorer] > [Open Folder]を押下
[上部のOpen Folder]でUbuntuで開きたいFolderを選択
[Do you trust the authers of the files in this folder?]が表示されたら、[Yes, I trust the authors]を押下

> Explorerに対象のFolder配下のファイルが表示されること


[Ctrl + @]を押下しTerminalを開き、以下のコマンドを実行

```
lsb_release -a
```

> 以下の通り、Ubuntuのバージョンが表示されること

```
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 24.04.4 LTS
Release:        24.04
Codename:       noble
```
