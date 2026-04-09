# Windows_Ubuntu_Node.md

## requirements

- Windows_Ubuntu.md

## install

Ubuntuを開き、以下のコマンドを実行

```
sudo apt update && sudo apt upgrade -y
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install nodejs -y
npm install -g npm@latest
node -v
npm -v
```

> 以下が表示されること

```
# node -v
v22.22.2
# npm -v
11.12.1
```

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
