# Dockerfileとは

DockerImageの元になるファイル（ソース）

# 作成方法（記述方法）

形式はテキストファイルなのでVim等で作成できる（ファイル名は頭大文字で'Dockerfile'にする）

### FROM

ベースとなるイメージを指定する

公式リポジトリから取得する方法が一番簡単

Dockerfileは上から順番に処理を実行するのでFROMは一番先頭に書く必要がある

### RUN

コマンドの実行（上から）

RUNの後に処理を羅列していく、各処理は`&&`でつなぐ、改行したいときは`\`入れる

sh(シェル)言語で書く（対話を受け付けないように -y などを使ってバッチ化する）

### CMD

CMDで記述すると `docker run` でコンテナを生成するときも実行される

記述方法はRUNと同じ

### ENV

環境変数の指定

変数名 値 の形式で記述

### ADD

ファイル/ディレクトリの追加

### VOLUME

ボリュームのマウント

### EXPOSE

ポートのエクスポート

# DockerfileからImageを生成する

` docker build -t [ImageName] [Dockerfileが置いてあるディレクトリパス]` でイメージを生成する

