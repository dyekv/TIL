# kubernetesとは

Dockerのコンテナを管理するためのOSS

クバネティスと読み、k8sと略されることが多い

googleやamazonといった企業でも使われており、コンテナ界ではメジャー

# minikube

kubernetesは複数のリソース（ノード）を管理するため複数のマシンが必要

シングルノード（PC1台）で手軽にkubernetesをお試しできるのがminikube

kubernetesの学習用のお試し版のようなもの

# docker for mac で kubernetesを使う

docker for mac にkubernetesを使う機能があった

kubernetesの `kubectl` コマンドが使える

# メリット

本番環境の作成が楽（クラウド上にあるので、外部に公開するサービスなどがメイン）

Paasを使うことでOSのインストールやパッケージのインストール、本番環境用の設定ファイルの作成などが不要

dockerの管理を楽にすることができる

アウトスケールが楽（ノードの追加時に設定が不要）

# やりたいこと(社内で)

`git push` しただけで本番環境も最新版に自動で置き換わるようにする

テスト環境・本番環境のPaaS化
