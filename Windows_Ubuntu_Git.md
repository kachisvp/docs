# Windows_Ubuntu_Git.md

## requirements

- Windows_Ubuntu.md

## install

Ubuntuを開き、以下のコマンドを実行

```
sudo apt update && sudo apt upgrade -y
sudo apt install git
git --version
```

> 以下が表示されること

```
git version 2.43.0
```

## settings

Ubuntuを開き、以下のコマンドを実行

```
# user
git config --global user.name "Namae Myoji"
git config --global user.email "mail@example.com"

# proxy

## **Proxy設定は、ProxyServer環境下でなければ設定不要**

git config --global http.proxy http://_proxy_:8080
git config --global https.proxy http://_proxy_:8080
git config --global url."https://".insteadOf git://

# branch settings
git config --global init.defaultBranch main

# reset settings
# git config --global --unset http.proxy
# git config --global --unset https.proxy

# confirm settings
git config --global --list
```

> 以下が表示されること

```
user.name=Namae Myoji
user.email=mail@example.com
init.defaultbranch=main
```

## commands

Ubuntuを開き、以下のコマンドを実行

```
git clone https://git-codecommit.ap-northeast-1.amazonaws.com/v1/repos/_repository_
git clone codecommit::ap-northeast-1://_repository_
```
