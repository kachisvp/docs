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
ex) user@'_pcname_':/mnt/c/Users/'_username_'
```

そのままUbuntuを開き、以下のコマンドを実行

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

## settings

### [~/.bashrc]を修正

Ubuntuを開き、以下のコマンドを実行

```
printenv http_proxy https_proxy no_proxy HTTP_PROXY HTTPS_PROXY NO_PROXY
cat ~/.bashrc
echo -e "\n# proxy settings" >> ~/.bashrc
echo 'proxy_server=http://_proxy_:8080' >> ~/.bashrc
echo 'export http_proxy=${proxy_server}' >> ~/.bashrc
echo 'export https_proxy=$http_proxy' >> ~/.bashrc
echo 'export no_proxy=127.0.0.1,localhost' >> ~/.bashrc
echo 'export HTTP_PROXY=$http_proxy' >> ~/.bashrc
echo 'export HTTPS_PROXY=$https_proxy' >> ~/.bashrc
echo 'export NO_PROXY=$no_proxy' >> ~/.bashrc
cat ~/.bashrc
source ~/.bashrc
printenv http_proxy https_proxy no_proxy HTTP_PROXY HTTPS_PROXY NO_PROXY
```

### [/etc/apt/apt.conf.d/proxy.conf]を修正

Ubuntuを開き、以下のコマンドを実行

```
su -
touch /etc/apt/apt.conf.d/proxy.conf

echo 'Acquire::http::Proxy "http://_proxy_:8080";' >> /etc/apt/apt.conf.d/proxy.conf
echo 'Acquire::https::Proxy "http://_proxy_:8080";' >> /etc/apt/apt.conf.d/proxy.conf

exit
cat /etc/apt/apt.conf.d/proxy.conf
```

> 以下が表示されること

```
Acquire::http::Proxy "http://_proxy_:8080";
Acquire::https::Proxy "http://_proxy_:8080";
```

## commands

コマンドプロンプトを開き、以下のコマンドを実行

```
# バージョン表示
wsl --list --verbose

# WSL停止
wsl --shutdown

# WSL uninstall
wsl --unregister ubuntu
```
