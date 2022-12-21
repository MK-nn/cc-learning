# cc-learning

# 開発環境
- 想定開発環境 x86-64
- macの場合は docker を使用する必要がある。

## docker の set up
1. [Docker Desktop for Mac](https://docs.docker.com/desktop/install/mac-install/)をインストールする
2. イメージの作成
```
$ docker build -t compilerbook https://www.sigbus.info/compilerbook/Dockerfile
```

## ビルド
```
$ docker run --rm -it -v ~/ghq/github.com/MK-nn/cc-learning:/cc-learning compilerbook
```
`-it`: インタラクティブに使用する場合 <br/>
`-v `: dockerの外で編集したディレクトリをdocker内から参照する

## コンテナを変更したい場合
```
$ docker run -it compilerbook

// 変更したい内容
$ sudo apt update
$ sudo apt install -y curl

// シェルから出る
$ exit

// コンテナIDの確認
$ docker container ls -a

// 変更をコミットする
$ docker commit <CONTAINER ID> compilerbook
```
