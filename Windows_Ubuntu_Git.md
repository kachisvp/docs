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
git config --global http.proxy http://'_domain_':8080
git config --global https.proxy http://'_domain_':8080
git config --global url."https://".insteadOf git://

# branch settings
git config --global init.defaultBranch main

# reset settings
# git config --global --unset init.defaultBranch

# confirm settings
git config --list
```

> 以下が表示されること

```
user.name=Namae Myoji
user.email=mail@example.com
init.defaultbranch=main
```
