# Rancher2.0 Kubernetes Workshop in Fukuoka #01

2019/01/12 Sat

さくらインターネット福岡さんにて

ハッシュタグ [#rancherjp](https://twitter.com/search?q=%23rancherjp)

[togetterまとめ](https://twitter.com/shindoy/status/1084260623750389760)

## 書籍

コンテナ・ベース・オーケストレーション

## 資料

[Introduction of kubernetes rancher
](https://www.slideshare.net/cyberblackvoom/introduction-of-kubernetes-rancher-127758994)

## trend

- Google Serverless containers 発表
  - Knative

- GitHubもkubernetesで
  - SREが話題になった

## What's kubernetes ?

### Architecture

- Master
  - etcd エトセディー
    - データストア
- Node
  - Kube-proxy
    - 窓口
    - iptable
  - Pod
    - Container
    - Volume
      - Container間で共有可能
    - 複数Nodeにまたがることはない
- Deployment, ReplicaSet
  - 定義した数のPodを常に起動する仕組み
- Service
  - L4
  - クラスタ内外からのアクセスをPodにルーティングする
- Ingress
  - L7
  - 外部トラフィックを内部にルーティングする
  - さらに上位にELBを配置するなどしても良い

サイバーエージェントが中心となってマニュアルの日本語訳を作成する動きもある

### RANCHER

- コンテナー環境の構築・運用プラットフォーム
- ノード、コンテナー管理、デプロイ
- 1系
  - Dockerベース
- 2系
  - kubernetesベース
  - DBはetcd
  - カタログ機能(Helm対応)によるワンクリックデプロイ
  - Latest 2.1.5
    - 1系から2系へのマイグレーション
    - Windows Kuberntes クラスタの実験的サポート
      - Windowsコンテナが動くらしい

LINE DEVELOPER MEETUPの資料

Create, Import, ManageがRANCHERの魅力的な機能

- rancher/rio
  - Knativeに近い
  - 開発者は意識したくない、難しいので簡単なものが欲しいよねという発想で作られた

Get started with Rancher

### workshop

各自割り振られたIPアドレスのマシンにログイン

```
$ # server
$ ssh -i ~/.ssh/rancherworkshop.pem ubuntu@xxx.xxx.xxx.xxx
```

```
$ # host
$ ssh -i ~/.ssh/rancherworkshop.pem ubuntu@xxx.xxx.xxx.xxx
```

- Qiita
  - Introduction of Kubernetes & Rancher2.0
    - https://qiita.com/cyberblack28/items/1f5cad99b7bb34b983e9

- dockerインストール
  - https://github.com/rancher/install-docker

Rancherサーバ
![](https://pbs.twimg.com/media/DwsI3LWVAAA4rth.jpg)

weavescope
![](https://pbs.twimg.com/media/DwsKyEnVYAAtlIk.jpg)

ブラウザ上でkubectlコマンドが叩ける
![](https://pbs.twimg.com/media/DwsMsFhUYAEdSNl.jpg)

guestbookをデプロイ
![](https://pbs.twimg.com/media/DwsNAYJUwAAK8cl.jpg)

weavescopeでguestbook(frontend)がデプロイできてることが確認できる
![](https://pbs.twimg.com/media/DwsN8BsUUAAgZ8Z.jpg)
