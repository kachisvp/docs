# Windows_Ubuntu_Node.md

## requirements

- Windows_Ubuntu.md

## install

Ubuntuを開き、以下のコマンドを実行

```
sudo apt update && sudo apt upgrade -y
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash
cat ~/.bashrc
source ~/.bashrc
nvm --version

nvm install 22
nvm use 22
nvm alias default 22

# npm自身のinstallはglobal installする。
npm i -g npm@latest

node --version
npm --version
which node
which npm
```

> 以下が表示されること

```
# nvm --version
0.40.4
# node --version
v22.22.3
# npm --version
12.0.1
# which node
/home/'_username_'/.nvm/versions/node/v22.22.3/bin/node
# which npm
/home/'_username_'/.nvm/versions/node/v22.22.3/bin/npm
```

## settings

**Proxy設定は、ProxyServer環境下でなければ設定不要**

Ubuntuを開き、以下のコマンドを実行

```
npm -g config set proxy http://'_domain_':8080
npm -g config set https-proxy http://'_domain_':8080
npm -g config set registry http://registry.npmjs.org/
npm -g config set strict-ssl false
# npm -g config delete proxy
# npm -g config delete https-proxy
# npm -g config delete registry
# npm -g config delete strict-ssl
npm -g config list
```

> 以下が表示されること

```
registry = "http://registry.npmjs.org/"
strict-ssl = false
```
