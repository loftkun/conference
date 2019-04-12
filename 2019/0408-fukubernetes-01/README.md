# #ふくばねてす node-1

2019/04/08 Mon

The Company 中洲川端さんにて

ハッシュタグ [#ふくばねてす ](https://twitter.com/search?q=%23%E3%81%B5%E3%81%8F%E3%81%B0%E3%81%AD%E3%81%A6%E3%81%99)

![](https://pbs.twimg.com/media/D3n2M82U8AAvr0U.jpg:large)

## ふくばねてすとは

- ロゴ募集！
- クラウドネイティブ
  - 高低差大きくていい
    - 気軽に話せる場
    - ガチなのもいい
- 会場
  - 夜景が綺麗

## 本当の"""負荷検知"""をお見せしますよ - cgroup v2 feat. PSI

Uchio Kondoさん

- cgroup と コンテナ
  - コンテナのリソース制限の基本技術
- cAdvisorはcgroupの情報をprometheusに見せるもの
- [ローファイ日記](https://udzura.hatenablog.jp/)

## 何と読む？謎のk3s

Shindo Yosukeさん

- 博多織の名刺入れ！
- Meetupやりすぎ男
- 5/3 に 勉強会
  - Cloud Native FUKUOKA #01
    - LTが空いているぞ！

- k8s.jp
  - 翻訳サイトのユニットやってます
- rke使うとオンプレにk8sをデプロイできる
- cyberblack28さんのQiita記事が分かりやすい

- k3s
  - light weight kubernetes
  - ishida330さんのQiita記事が分かりやすい
  - GoalはEdgeとかIoT
  - CNDF製なのでパチモンじゃないよ
  - 何をマイナスしたのか
    - inductorさんのQiita記事が分かりやすい
  - k3s.io
  - github.com/rancher/k3s

- k3sもくもく勉強会
  - 大阪で始まっている
  - 福岡でも！

- rancherのslcak
  - k3sチャンネル
  - ビギナーズチャンネル

## kokotapでPodのパケットキャプチャ

Takayuki Konishiさん(Red Hat)

- OpenShift
  - kubernetesをRed Hatが拡張
  - 会社としてはkubernetesへのコミット数2位
- コンテナ上の製品をサポートするのでパケットキャプチャができるとよいのかな
  - kokotapというものがあるらしい
    - 動かない・・・
      - 東京出張で開発者に会った
        - podの中のパケットをキャプチャできる
    - サービスメッシュの場合、Podから送信するパケットは書き換えられているが、変更前のパケットをキャプチャできる

## telepresenceにキャッチアップ - 後藤さんを倒すには - （仮題）

kunitさん (ペパボ)

- k8sを触り始めて一週間！
- Cloud Native Meetup Tokyo #7のキャッチアップです
- タイトルはうづらさんの勢いでつけた
- telepresence
  - k8sクラスタに接続して一部のサービスをローカルのものに置き換えて実行ができる
  - ローカルの開発環境をk8s clusterの一部にできる
    - imageをregistoryにpushしてpodを更新する手間が省ける
  - 動かし方
  - デモ


## いっぱい kustomize する

iwaさん

- 読みは？
  - カスタマイズ？
  - クスタマイズ？
  - コミュニティで決めてもらえれば
- kustomize
  - kubernetes-sigs
  - vs helm
  - マニフェストの再利用がしやすくなる
- デモ
  - dev
  - prod


## Secure your K8s cluster from multi-layers

Transnanoさん

- なぜk8sのセキュリティは難しい？
- Infrastructure Layer
- k8s Control Plane Layer
- Admission Control
- k8s Workload Layer
- Pod Security Policy
- RBAC
- Yes! We are hiring!


## Enjoying k8s clusuer with Minikube and Helm

私(loftkun)の発表
[Enjoying k8s cluster with Minikube and Helm](https://speakerdeck.com/loftkun/enjoying-k8s-cluster-with-minikube-and-helm)

## Falcoを触ってみた

## buildpack、そう、そういうことなんだ俺たちのこれからは

- みなさんはCloud Nativeですか？
- ペパボの現状
  - オンプレOpenStack + オンプレホスティングサービス
- Cloud Nativeに移行して解決したいこと
- Heroku
- buildpack
  - アプリケーションのソースを判断






