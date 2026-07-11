# Windows_Ubuntu_template.md

## requirements

- AWSCDK_Bootstrap.md
- Windows_Ubuntu.md
- Windows_Ubuntu_Git.md
- Windows_Ubuntu_Node.md
- Windows_Ubuntu_VSCode_RemoteDevelopment.md

## install

### AWS CLI

Ubuntuを開き、以下のコマンドを実行

```
sudo apt update && sudo apt upgrade -y
cd ~
sudo yum remove awscli
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
sudo apt install unzip
unzip awscliv2.zip
sudo ./aws/install
aws --version
rm -rf awscliv2.zip aws
```

> 以下が表示されること

```
aws-cli/2.34.28 Python/3.14.3 Linux/5.15.167.4-microsoft-standard-WSL2 exe/x86_64.ubuntu.24
```

### npm

[Windows_Ubuntu_Node.md]にてインストール済み

### aws configure

Ubuntuを開き、以下のコマンドを実行

```
aws configure_
AWS Access Key ID [None]: _access_key_
AWS Secret Access Key [None]: _secret_access_key_
Default region name [None]: ap-northeast-1
Default output format [None]: json
```

以下のコマンドで設定を確認

```
aws configure list
aws sts get-caller-identity
```

> 設定が表示されること
