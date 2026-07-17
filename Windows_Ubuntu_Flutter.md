# Windows_Ubuntu_Flutter.md

## requirements

- Windows_Ubuntu.md
- Ubuntu 上で Git / curl / unzip / zip などが使えること

## install

Ubuntu を開き、以下のコマンドを実行します。

```bash
mkdir -p ~/dev
cd ~/dev
git clone https://github.com/flutter/flutter.git -b stable flutter
```

## path settings

Flutter コマンドを使えるように PATH を追加します。

```bash
echo 'export PATH="$HOME/dev/flutter/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

## prerequisites

Flutter の開発に必要なパッケージをインストールします。

```bash
sudo apt update
sudo apt install -y git curl unzip xz-utils zip libglu1-mesa clang cmake ninja-build pkg-config libgtk-3-dev liblzma-dev
```

## verify

インストール後に以下を実行して確認します。

```bash
flutter --version
flutter doctor -v
```

## notes

- Windows 側の Flutter SDK を Ubuntu から直接呼び出すと、WSL/Ubuntu 環境では不安定になることがあるため、Ubuntu 側に Flutter SDK を別途入れる構成が推奨です。
- `flutter doctor` で追加の依存関係エラーが出た場合は、その内容に応じて必要なパッケージを追加してください。
