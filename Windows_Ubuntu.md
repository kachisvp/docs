# Windows_Ubuntu.md

## install

コマンドプロンプトを開き、以下のコマンドを実行

```
wsl --list --verbose
```

> 以下が表示されること

```
Linux 用 Windows サブシステムにインストールされているディストリビューションはありません。
この問題を解決するには、以下の手順に従ってディストリビューションをインストールしてください:

'wsl.exe --list --online' を使用して利用可能な配布を一覧表示する
および 'wsl.exe --install <Distro>' を使用してインストールしてください。
```

コマンドプロンプトを開き、以下のコマンドを実行

```
wsl --install -d Ubuntu
```

> 以下が表示されること

```
ダウンロード中: Ubuntu
インストール中: Ubuntu
ディストリビューションが正常にインストールされました。'wsl.exe -d Ubuntu' を使用して起動できます
```

コマンドプロンプトを開き、以下のコマンドを実行

```
wsl.exe -d Ubuntu
# [Create a default Unix user account: ]が表示されたら、[user]を入力
# [New password: ]が表示されたら、[_任意のパスワード_]を入力
# [Retype new password: ]が表示されたら、上記の[_任意のパスワード_]を入力
```

> Ubuntuのプロンプトが表示されること

```
ex) user@H370:/mnt/c/Users/'_username_'
```

そのままUbuntuを開き、以下のコマンドを実行

```
lsb_release -a
```

以下の通り、Ubuntuのバージョンが表示されること

```
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 24.04.4 LTS
Release:        24.04
Codename:       noble
```

以下のコマンドを実行し、Ubuntuを抜ける

```
exit
```

> コマンドプロンプトのプロンプトが表示されること

```
ex) C:\Users\'_username_'\
```

そのままコマンドプロンプトを開き、以下のコマンドを実行

```
wsl --list --verbose
```

> 以下が表示されること

```
  NAME      STATE           VERSION
* Ubuntu    Stopped         2
```
