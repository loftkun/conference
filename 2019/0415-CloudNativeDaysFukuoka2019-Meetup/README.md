# CloudNative Days Fukuoka 2019 Meetup

2019/04/15 Mon

[CloudNative Days Fukuoka 2019 Meetup｜EventRegist（イベントレジスト）](https://eventregist.com/e/cndf2019meetup)

LINE Fukuoka株式会社さんにて

ハッシュタグ [#CNDF2019](https://twitter.com/search?q=%23CNDF2019)

![](https://pbs.twimg.com/media/D4L4ZvUU0AIEAZy.jpg)


## 乾杯

- 草間さん CNDTのオーガナイザーの方
  - 3分前に音頭頼まれたらしい
- うづらさん遅れてくるだと・・・！？
- LINE 岸田さんから会場について

## Side Story: How we implement L7 networking on k8s

LINE Fukuoka Fujishima さん

- 明日話すセッションの一部
- Verda
  - Calicoを使った
    - BGPを使ってIP Routingをするすごいやつ
    - podのIPをシュッとアドバタイズする
    - それによりpodがLBとして機能する
- サーバからクライアントへはDSR方式
  - [DSR（Direct Server Return）とは](https://www.infraexpert.com/study/loadbalancer12.html)
  - 直接サーバからパケットが返る

## 乗ってけ！ServiceMesh 出発進行 Istio !

[nwiizo(@nwiizo)さん | Twitter](https://twitter.com/nwiizo)

- 可観測性
- サービスメッシュを導入した
- Istio
  - BookInfo
    - ぜひやってほしい
  - オライリー Istio Up & Runnning が出るらしい
    - [Amazon | Istio: Up and Running: Using a Service Mesh to Connect, Secure, Control, and Observe | Lee Calcote, Zack Butcher | Network Administration](https://www.amazon.co.jp/Istio-Running-Service-Connect-Control/dp/1492043788)
- LINKERD
  - スタンドアロンのプロキシ

- 質問
  - BookInfoの次に動かすと良いものは？
    - オライリー Istio本
    - Knativeのコードを読む

# 10分でだいたい分かるHelm

[バルゴ@福岡4/15-17(@go_vargo)さん | Twitter](https://twitter.com/go_vargo)

- 技術書店6にHelm本出した
  - [自作アプリをHelm化して簡単デプロイ - go-vargo - BOOTH](https://go-vargo.booth.pm/items/1313526)
- Helmのコマンドなど
  - sub chart
    - requirement.yaml、helm dependencyで管理
  - Hooks
    - インストール前後にjob実行、ConfigMapなど
  - Plugin
    - helm diff
  - helm lint
  - helm test
- Helm v3 が出ると結構変化があるらしい
  - tillerがなくなるらしい

質問
- ベストプラクティス、初心者はこうしろ、みたいなものは？
  - Helmの公式ページにベストプラクティスがある
    - Values.yamlの書き方とか

## showKsの話

Pivotal Japan !

[Kazuto Kusama(草間 一人) @技術書典6 う50(@jacopen)さん | Twitter](https://twitter.com/jacopen?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor)

- showKs
  - フォームにユーザIDとか入れると
  - 以下が専用で用意される
    - お絵描きできるキャンバス
    - GitHub
    - CI/CD、spinnnakerのパイプライン
  - ポータルでみんなの絵が見える
- CNCFのlandscapeの画像
- Interopのshow netからインスパイヤされた
- showks一緒にやってくれる人募集！

質問
- showKs
  - お絵かきアプリと同じものはやらないつもり
  - k3sとか


## 俺の中で今完全にAlgoCDが熱い！！！（pyama86）

GMO ペパボ！
[P山(@pyama86)さん | Twitter](https://twitter.com/pyama86?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor)

- ArgoCD
  - GitOptsなワークフローを実現するCD
  - デプロイは、helm, Kustomize, ksonnetなどで定義が可能


## 懇親タイム

ピザが届いたぞ！

うづらさんによる乾杯


## Custom Controller

GMO ペパボさん！

- CRD
- private cloudとして、OpenStack上にkubernetesがある
  - openstack-sg-contoroller
    - kubernetesのノードにSecurityGroupをアタッチするためのcontoroller
    - ブログ見てね
- kube-builderで作ったらしい
  - [kubernetes-sigs/kubebuilder: Kubebuilder - SDK for building Kubernetes APIs using CRDs](https://github.com/kubernetes-sigs/kubebuilder)

## RANCHER 2.2

[cyberblack(@cyberblack28)さん | Twitter](https://twitter.com/cyberblack28)

- What's RanchAnthoser？
  - LINEの方のdeep dive ソース全部読み解いた資料が参考になる
- 
- Rancher Labs
  - 深センにある
- k3s cluster importをサポート！

## 突撃！お隣のkubernetes事情

Cyber Agent !
[MasayaAoyama（青山 真也）(@amsy810)さん | Twitter](https://twitter.com/amsy810)

- Kubernetes完全ガイドの著者
- What is Cloud Natie ?
  - Cloud Native != kubernetes
   - Lambda, CFなどもあるよ
- CyberAgentにおける取り組み
  - AbemaTV
  - GKEを使うことが多い
  - AKE : Adtech Conainer Engine
    - 恐竜のキャラの名前はアクーエ
- 規模
  - 通常のサービス
    - 31〜50 ノード
- 16コアのインスタンス
- ログの転送方法のパターン
  - アプリからPub/sub
  - Fluentdを各ノードにdeamonsetとして配置
  - pod毎にsidecarとしてinject
- GCPのpersistent領域をマウントしてそこに吐く
- GKE node pool
- GKEの自動修復機能
- クラスタの自動アップグレードは無効化している
- みんなのDocker/Kubernetes
  - [みんなのDocker/Kubernetes：書籍案内｜技術評論社](https://gihyo.jp/book/2019/978-4-297-10461-0)


















