# MacOSでpyenvを使用して最新と一つ前のPythonをインスールする方法

## pyenvとは
pyenvとは、Pythonの標準の言語処理系が持つ機能の一つで、システム上に複数バージョンのPythonを同居させて使い分けられるようにするもの。

Python 2系と3系の使い分けなどを手軽に行うことができる。

### pyenvのインストール事前準備
1. Homebrewのインストール
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
2. インストールが完了したら下記コマンド投入
```
brew -v
```
バージョンが表示されたら成功！

### pyenvのインストール
1.pyenvのインストール
```
brew install pyenv
```

2.パスを通して、pyenvコマンドを実行できるようにする。

```
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
```
```
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
```
```
echo 'eval "$(pyenv init -)"' >> ~/.zshrc
```

下記コマンドを投入し、.zshrcが追記されていることを確認
```
cat ~/.zshrc
```

追記されていることを確認したら、以下のコマンドでシェルの設定を反映します。
```
source ~/.zshrc
```

3.パスを通してから下記コマンドでpyenvがインストールされていることを確認する。
```
pyenv -v
```
バージョンが表示されたら成功！

### Pythonのインストール
1. 下記コマンドでインストール可能なPythonのバージョン一覧を表示する。
```
pyenv install --list
```
2. Pythonのリリースされた最新版をインストールする。
現在(2024/03/29)では『3.13-dev』
```
pyenv install 3.13-dev
```

3. 下記コマンドでpythonのインストールを確認。
```
pyenv versions
```

『3.13-dev』の出力があれば成功！

**バージョンを追加する場合は、Pythonのインストール手順からバージョン名を変更する。**
