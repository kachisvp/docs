# Windows_Ubuntu_Python.md

## requirements

- Windows_Ubuntu.md
- Windows_Git.md

## install

Ubuntuを開き、以下のコマンドを実行

```
sudo apt update && sudo apt upgrade -y
# 後の[pyenv install 3.13.13]で失敗するため、installする
sudo apt install build-essential libbz2-dev libdb-dev libreadline-dev libffi-dev libgdbm-dev liblzma-dev libncursesw5-dev libsqlite3-dev libssl-dev zlib1g-dev uuid-dev tk-dev -y
# sudo apt remove build-essential libbz2-dev libdb-dev libreadline-dev libffi-dev libgdbm-dev liblzma-dev libncursesw5-dev libsqlite3-dev libssl-dev zlib1g-dev uuid-dev tk-dev -y
git clone https://github.com/pyenv/pyenv.git ~/.pyenv
cat ~/.bashrc
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init -)"' >> ~/.bashrc
cat ~/.bashrc
source ~/.bashrc
pyenv --version
```

> 以下が表示されること

```
pyenv 2.6.27
```

Ubuntuを開き、以下のコマンドを実行

```
# installするPythonのversionを確認
pyenv install --list | grep -v "[a-z]"
# [3.13]系の最新をinstall
pyenv install 3.13.13
pyenv versions
pyenv global 3.13.13
python -V
pip -V
```

> 以下が表示されること

```
# python --version
Python 3.13.13
# pip --version
pip 26.0.1 from /home/user/.pyenv/versions/3.13.13/lib/python3.13/site-packages/pip (python 3.13)
```
