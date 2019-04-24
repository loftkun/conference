# CloudNative Days Fukuoka 2019

2019/04/16 Tue

[CloudNative Days Fukuoka 2019｜EventRegist（イベントレジスト）](https://eventregist.com/e/cndf2019)

アクロス福岡にて

ハッシュタグ [#CNDF2019](https://twitter.com/search?q=%23CNDF2019)

![](https://pbs.twimg.com/media/D4PJiJYU8AE9V10.jpg)


## Keynote

### Welcome Talk From Fukuoka by Uchio Kondo (CNDF2019 chair)


### 飛び込もう、Cloud Nativeの世界 by Kazuto Kusama (JapanContainerDays best speaker)

Pivotal Japan の草間さん

[Kazuto Kusama(草間 一人) @技術書典6 う50(@jacopen)さん | Twitter](https://twitter.com/jacopen?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor)

[飛び込もう、Cloud Nativeの世界 - Speaker Deck](https://speakerdeck.com/jacopen/fei-biip-mou-cloud-nativefalseshi-jie)

- クラウドネイティブとはマイクロサービスであるみたいな言い方をされた時にどう思いますか？？
- クラウドネイティブは大規模なサービスでしか意味のないものだろうか？
- CNCFによるクラウドネイティブの定義
- Benefit
- クラウドの本質？
  - 一言で応えるなら`クラウドは人間を強化(エンフォース)する`と答えたい
- かかる時間
  - ナノ、マイクロ、ミリの世界
    - L1キャッシュ参照
    - カリフォルニア - オランダ間で通信1往復
  - 上司の許可を取ってサーバを1台調達する
    - 桁違いに時間がかかる
- Orchestration
- 運用
  - NoOpts
    - No Unconfortable Opts
  - ボールを走らせよ、ボールは疲れない
    - クラウドを走らせよ、クラウドは疲れない
  - 復元力の高いプラットフォーム

![](https://pbs.twimg.com/media/D4PNRrOUcAAI_RL.jpg:large)

- Kubernetesに限る必要はない
  - Serverless
  - PaaS
  - マネージドサービス
- MicroServicesは？
  - 価値を産み出すのは人間だけ
  - いいサービスを作れるのは人間だけ
  - ある程度の規模を超えるとシステム的にも組織的にもスケールしなくなってくる
    - そこでMicroServices
      - 詳細はこの後に続くセッションで！

![](https://pbs.twimg.com/media/D4POK5kUwAETSKW.jpg:large)

- Cloud Native Trail Map
  - [cncf/trailmap: TrailMap files from the cncf/landscape repo](https://github.com/cncf/trailmap)
  - [CNCF Cloud Native Interactive Landscape](https://landscape.cncf.io/)

### CacooのKubernetesによるマイクロサービスアーキテクチャ by Kohei Kimura / Nulab

ヌーラボ [Kohei Kimura(@cohhei)さん | Twitter](https://twitter.com/cohhei)

- LTかと思っていた
- あわててkubernetes 実践入門を購入！

- kubernetesについて
- EC2期 --> ECS期 --> k8s期
- 構成
  - envoyを使ってGRPCの通信をプロキシ
  - rabbitMQ
  - elastic search, kibana
- 依存関係が下がった
  - 変更がしやすくなった
  - デプロイ・ビルドが高速
  - 福岡、海外のチームが独立
    - タイムゾーンが違うことのメリット

## Kubernetesはキャズムを超えるのか by Shingo Kitayama / Red Hat (gold sponsor)

Red Hat Openshift ソリューションアーキテクト

[Kubernetes Crossing the Chasm - Speaker Deck](https://speakerdeck.com/shkitayama/kubernetes-crossing-the-chasm)

- SANDBOX
- INCUBATING
- GURADUATE
  - k8s
  - prom
  - envoy
  - CoreDNS
  - containerd
  - Fluentd
- 日本市場でk8s使ってるってどんなもんですかね？
  - 本番でk8s使ってる人どれくらいいますか？
  - パブリッククラウド(AWS/Azure/GCP/etc)使ってる方？
    - 結構いる
    - キャズムを超えている
  - k8sはまだまだキャズムは見えてないのではないか
　 　- エッジソリューション(補助的な製品)が市場に登場し、成熟していく
- キャズムを超えるとは
  - 属人的な運用で解決してきた安心感をテクノロジーで置き換える
    - Early Adapter
      - 製品を中心とした価値観
    - Ealry Majority
      - 市場を中心とした価値観
- OpenShift
  - OperatorHub.io
  - 3rdパーティによるサポート
- OpenShift User Group
  - 5/22 福岡をリモートで繋ぎます
    - [OpenShift Meetup Tokyo #4 - connpass](https://openshift.connpass.com/event/127775/)

## Kubernetes を利用したコンテナ開発のススメ by Taiga Murakami / Google Cloud (gold sponsor)

Google Cloudの方！

- Google Cloud 知ってる方？
  - 触ったことある方？
    - 結構多い
- コンテナ開発が注目される背景
- GCPが提供するソリューション
  - GKE
- サービスメッシュ
  - Istio
- Cloud Service Platform
  - 昨年 Nextで発表した
  - 今年 `Anthos` という名前にかえてアナウンスした
    - GKE On-Prem
- Google Cloud Next Tokyo
  - 7末にあるよ

## 昼休み

### お弁当

![](https://pbs.twimg.com/media/D4PgL8RUYAAZ16v.jpg)
![](https://pbs.twimg.com/media/D4PgMcIUcAAEBRI.jpg)

### 会場トランスフォーム

![](https://pbs.twimg.com/media/D4Pgkd0UcAErT3F.jpg)

### ブース&グッズ

![](https://pbs.twimg.com/media/D4Po_G8UEAETgSx.jpg)
![](https://pbs.twimg.com/media/D4P04IqUcAA6Ai1.jpg)
![](https://pbs.twimg.com/media/D4P1GsAU4AEgW5h.jpg)
![](https://pbs.twimg.com/media/D4P1TPZUIAA16bj.jpg)


## [Room A] CircleCI 2.0を支える2つのコンテナ・オーケストレーションツール by Hirokuni Kim / CircleCI (silver sponsor)

- 今日の話
  - ベアメタル
  - 仮想マシン
  - コンテナ
- 物理 vs 仮想マシン vs コンテナ
- A社の出来事
  - コンテナとk8sを採用することを決定
  - k8sをベアメタルで動かす判断をした
  - 物理上でk8s使ってるとハードリソースの利活用ができない
    - 大きなシングルクラスタになりがち
- 仮装インフラ(VSphera)上なら物理とクラスタは1:1マップする必要がない
  - 同一ハードに別のクラスタが乗っててもよく、ハードリソースを効率的に使える
  - HAがある
  - DRSがある
    - ハイパーバイザーがより下のレイヤでワークロード配置を最適化する
- CNCF Survey conducted in Marh and November 2018
- VMware PKS
  - オンプレ
  - ハイブリッドクラウド
  - パブリッククラウド

## [Room A] Kubernetes and Beyond by Yusuke Kuoka / Z Lab Corporation

(バッテリーあと10%)

Z Lab !

[Yusuke KUOKA(@mumoshu)さん | Twitter](https://twitter.com/mumoshu/)

- メンテナ
  - helmfile とかいろいろ

- Can't We Automation more ?
  - Domain-specific Automations
  - Kubernetes Operator Pattern
    - Is Operator Only Solution ?
- 昔は
  - shell script で 自動化
    - 今はより複雑化している
    - スクリプト化できるほど単純でない
- kubectl run
  - what happens run k8s
  - これでshellのコマンドが実行できるよね
  - 並列実行は？
- sync file
  - pattern ( l : local, c : container )
    - l -> c
    - c -> l
    - c -> c
  - kubectl-wrap
    - kubectl run + rsync
  - kubectl-biwarp
- shell script、デファクトなパッケージマネージャがない
- まじなプログラミング言語でいけないか？
  - Brigade
     - [Brigade | Event-driven scripting for Kubernetes.](https://brigade.sh/)
     - Brigade script
       - jsで書ける

(バッテリーあと5%)

- Event Gateway
- Knative Eventing
- Scripting Platform が来て欲しい

## [Room A] A story of migration from Docker-swarm to Kubernetes by Shigeyuki Fujishima / LINE Fukuoka (silver sponsor)

(バッテリーあと3%、まもなくリアルタイムメモを終わります)

## [Room A] NoOpsを目指してKubernetesネイティブな物理データセンターを作るサイボウズの取り組み by Hirotaka Yamamoto / Cybozu

(このセッションの頃には多分バッテリーが切れてると思う)

## [Room A] Datadogで実現するこれからのコンテナ監視 by Kunihiko Ikeyama / Datadog (silver sponsor)

(このセッションの頃には多分バッテリーが切れてると思う)

## After Party




