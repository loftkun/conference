# CloudNative Days Kansai 2019

2019/11/28 Thu

コングレコンベンションセンター

ハッシュタグ [#openshiftjp](https://twitter.com/search?q=%23CNDK2019)

## keynote

### 10:00 - 10:30 コンテナの作り方～Dockerは裏方で何をしているのか～

[前佛 雅人 - Masahito Zembutsu（@zembutsu）さん](https://twitter.com/zembutsu)

- 名前空間によるisolate
- cgroupによるリソース制限

![](https://pbs.twimg.com/media/EKbCnCLUYAIe4Ki?format=jpg&name=large)

### 10:30 - 10:50 メルペイのマイクロサービスとCloud Native

[@tjunさん](https://twitter.com/tjun)

俺たちは雰囲気でクラウドネイティブをやってる

- マイクロサービス
  - プラットフォーム運用側
    - namespaceを使って各サービスを分けている
  - 開発チーム
    - 各チームは自分のサービスを意識して作る

- k8sにreconcileあるけど、
  - その考えと同じような感じでこの値になるべきというループでバッチ的な処理を回しているよ

- SRE
  - SLOを決めておく
    - エラー発生時の対応判断に使う
  - Observability
    - metrics
    - trace
    - log

- 課題
  - 一部のマイクロサービスがモノリス化する
  - QAが難しい
    - どのマイクロサービスのどのバージョンの組み合わせなのか
  - 運用と開発のリソースの調整

- クラウドネイティブで重要なのは技術でない
- 組織体制や開発・運用のスタイルも含めたCulture

### 11:00 - 11:20 Anthos が描く新しいアプリケーションプラットフォーム


[Kazuu（@kazshinohara）さん / Twitter](https://twitter.com/kazshinohara)

- 「アンソス」
  - 古代ギリシャ語で花という意味
    - 花開かせたいという思いをつけている
  - googleでは古代ギリシャ語をつける慣習がある
    - k8sもそう
    - わかりにくいという社内の声もあるぞ
- 中の人でも一言でまとめるのは難しい
  - k8sをベースにしたアプリケーション管理プラットフォーム
  - GKEをGCPのみならず、オンプレミス、他社クラウドで動かす
- まだ発展途上
- 抽象度高めて分類すると
  - サーバレス
  - マーケットプレイス
- ちょい具体的にすると
  - クラスター管理
  - ポリシー管理
    - RBAC
    - namespace
  - サービス管理
    - メッシュ

#### クラスター管理

- GKE On-Prem
  - VMWare vSphere 6.5環境上で動作するマネージドのk8s
  - AdminクラスタがUserクラスタを管理する構成になっている

- 「キューブコントロール」と呼んでるなあ

- GCP ConsoleでGCP、オンプレ、他社クラウドを管理できるようになる予定

- Demo - GKE On-Prem
  - VMWare ESXiの画面

- オンプレ側にAgentが動いていてそれを収集してGCPのConsoleに表示されてるんだよ

#### ポリシー管理

- namespace, quata , 

- Demo - ACM
  - 左console で yamlを編集してRoleにユーザ追加して、git push 特定のブランチ ってやると
  - 右console それに紐づいてるクラスタ側にそれが反映されたぞ kubectl get rolebinding --watch 的に見せた

- Anthos Service Meshの構成

- Demo ASM Observability
  - マイクロサービスのトポロジグラフをダッシュボードで描画できるぞ
  - マイクロサービスが増えた時にほんとに描画できるの？という懸念はあるかも
  - マイクロサービスごとにSLOの数値を設定できるぞ！

- 「アンボイ」と呼んでるなあ

- 1/30 Google Cloud k8s day 渋谷


### 11:20 - 11:40 MackerelにおけるCloudNativeへの継続的な取り組み 〜オンプレからCloudNativeまで〜

[まさよし（@yoyogidesaiz）さん / Twitter](https://twitter.com/yoyogidesaiz)

- Mackerel
  - はてなが開発してるPrometheus的なやつ


## セッション

### 12:20-13:00 クラウドサービス開発・運用の落とし穴教えます

[後藤隊長（@boot_vmlinuz）さん / Twitter](https://twitter.com/boot_vmlinuz)


### 13:20-14:00 1年間のシステム運用を通して分かったIstioの嬉しさと活用における注意点

[id（@ido_kara_deru）さん / Twitter](https://twitter.com/ido_kara_deru)

- 日立製作所 研究開発

- 日立では社内システム向けにIstioを導入して1年に渡って運用

- なぜServiceMeshが求められるのか？
  - それにはマイクロサービスの説明から入る必要がある
    - マイクロサービス
      - Death Star Diagram
  - どう運用するか？
- [servicemesh.es | Service Mesh Comparison](https://servicemesh.es/)
- Istio
  - Traffic Management
  - Security Management
    - サービス間認証
      - mTLS
        - サーバ、クライアント双方が証明書で互いを認証する
          - ゼロトラストネットワークとかの文脈でよくでてくる
            - 受信
              - Policyで設定
            - 送信
              - DestinationRuleで設定
    - 認可
      - L7レベルのアクセス制御
      - rewirteAppHTTPProbers
  - Observability

- 社内でのIstio活用ケース
  - 社内開発者向けに開発環境を提供するサービス
    - Webエディタやバックエンドサービスなどを提供
    - バックエンドサービスは各チームが自律的に開発
    - 100+ Nodes, 2000+ Pods
  - 検証も兼ねてIstioを導入
    - 本番環境で1年ほど運用

- 良かった点
  - 個々のサービスを改修しなくて良い
  - 柔軟・高機能な通信管理
  - k8s ネイティブ
  - コミュニティが大きく、活発
    - Issueの平均対応時間 : 5日
      - Istio Project Dashboard
        - [Time to triage an issue - IO Istio DevStats](https://istio.teststats.cncf.io/d/57/time-to-triage-an-issue?orgId=1&from=now-90d&to=now)

- 注意点
  - 使用難度が高い
  - 障害時の原因切り分けが困難
    - 対策
    - 社内向けIstio情報共有Wiki
    - 3ヶ月毎のアップデートが必要
      - Istio Operator
        - 現在はインストール、アップデートがメイン
          - インストール時複雑な設定が必要なのを隠すAPIを提供
        - Helmによるインストールは廃止予定
  - サービスとプラットフォームの境界
    - Helm Chart化してサービスチームに使ってもらった
  - proxyのメモリ消費
    - pod数が多くなると問題に
      - ダミーpod 50個から500個まで増やしリソース使用量の近似式を作った
        - コミュニティに提案予定
    - ちなみに、Istioのバージョンが上がるごとにメモリ使用量は下がっている
  - 認証認可のマイグレーション

### 14:20-15:00 創るものから活用するものへ -価値を生み出すOperatorの力-

[Kazu @capsmalt（@capsmalt）さん / Twitter](https://twitter.com/capsmalt)

- kubernetesの保守は難しい
- Operatorが一つの解になりうる

- 今日の目的
  - すでにある Operator から逆算して、用途を理解する
  - 創るのか、活用するのか、見定める術を知る

- k8s基本動作
  - ReplicaSet Controller
    - Control Loop(Reconciliation Loop)
  - k8s controller たち
    - ReplicaSet
    - Deployment
    - etc,,

- Why/What
  - operator
    - custom controller
    - custom resouce
  - 運用を個別に対応する時代は終焉
    - k8sの能力であらゆるものを自動化
  - k8sクラスターの維持管理
  - 運用の知見をコード化し、自動化
    - etcd operator
    - postgres operator
    - Rook
      - SDSと連携したOperatorとして稼働
    - Meta Operator
      - OperatorのOperator
- How to get
  - 創る
    - Zラボ
     - 「kubernetes operatorで実現するNoOpsの世界」
     - ツール
       - Kubebuilder
       - Operator SDK
       - バルゴさんの本
  - 活用する
    - OperatorHub
      - Operatorの成熟度モデル

- omake
  - Operatorのライフサイクル管理
    - Operator Lifecyle manager

- 宣伝
  - Openshift.Run 2019
    - 12/20 恵比寿


### 15:40-16:20 Kubernetesの運用を支えるGitOps

[レンジ（@renjikari）さん / Twitter](https://twitter.com/renjikari)

- freeさん
- 1サービスの環境=1クラスタとしている
  - 開発チームに多くの権限を移譲し、自律的な運用を目指している
- GitOpsとは
  - weaveworks
  - OpsのGit化だ！
- k8sは全ての設定がmanifestとしてコード化されてる
- ガイドライン
  - コードとして記述できるものは全てGitに保存
  - kubectlを使用しない
  - オペレータパターンに従ってコントローラを使う
- ツールいくつかあるよ
  - argo
  - flux
    - k8s上のflux系のpodがリポジトリをwatchしてる
- free
  - PRのコメントがトリガー
    - create cluster とか
  - clusterops というコマンドを書いた
    - Helmfileやeksctlをラッパーしてる
    - variantというOSSを利用して書いている
- 運用上の課題
  - 複雑な構成でキャッチアップが大変
  - [TODO] helmfileって何ができるんだっけ

### 16:40-17:20 早い・安い・うまい！〜RancherによるKaaS事例集〜

[ShindoY@Rancher🇯🇵（@shindoy）さん / Twitter](https://twitter.com/shindoy)

- どこでもkubernetes
  - LINEさん
  - 海外では
    - Disney
      - 映像配信PF
- Rancher
  - Rancher Labsのチンさんからの発表
  - CUIツール rke
  - k3s
  - k3os
    - k3s実行に特化した軽量OS
- Rancherを使ったk8s運用
  - Alpaca Japanの方
    - 金融、機械学習
- KAGOYA CLOUDコンテナサービスのご紹介
  - [Shuji Hisaoka（@ShujiHisaoka）さん / Twitter](https://twitter.com/shujihisaoka)
  - KAGOYAとRANCHERの出会い
  - サインアップ含めて10分くらいあればクラスタができる

### 17:40-18:20 Production Ready Kubernetesに必要な15のこと

[バルゴ（@go_vargo）さん / Twitter](https://twitter.com/go_vargo)

- CICD
  - CI
    - GitLab
  - CD
    - Spinnaker
- Manifest Management
  - Mono Repository or Multi Repository
  - Helm
  - Kustomize
- Monitoring
- Initial Processing 初期処理
- Graceful Shutdown
  - 突然のプロセス終了に対して堅牢であるべき
  - これしっかりやらないと5xx系エラーがでてしまうぞ
- HealthCheck
  - livenessprobe
  - readinessprobe
- Config Injection
  - ConfigMap
  - Secret
    - base64なので、よりセキュアに管理するにはk8s以外のソリューションが必要
      - vaultとか
- Maintenance & Upgrade
  - kubectl drain
  - PodDisruptionBudget Resouce
- Resouce Management
- Scheduling
  - 










