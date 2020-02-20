# OpenShift Meetup Tokyo #5

2019/07/24 Wed

九州ビジネスソリューションズ株式会社 QBS-Labさんにて

ハッシュタグ [#openshiftjp](https://twitter.com/search?q=%23openshiftjp)

## 猿でもわかる Operator

- Operatorって何？
  - 1 誰がやっても同じ方法でできる
  - 2 然るべき方法で監視
  - 3 ベンダから提供されるUPDATE

- Operatorが機能を提供する対象
  - Podやそれにまつわるリソース(ConfigMap, Secret,,,)
- OperatorはすなわちController

- 猿にはまだ早すぎた・・・

- 

## Elastic Cloud on Kubernetes(ECK)をOCPに入れてみた  ～Operator導入時の「OpenShiftあるある」なつらみ～

OCP : OPENSHIFT CONTAINER PLATFORM

[OCP Meetup Tokyo #05 ECK on OCP](https://www.slideshare.net/TetsuyaSodo1/ocp-meetup-tokyo-05-eck-on-ocp-157494511)

- Operatorとは何か
  - SREを実現
- ECKとは何か
  - 5/21 アルファリリース
    - 対象はGKEとvanilla k8s
  - Elastic社提供
    - Elastic Stack
    - Elastic Cloud
    - コンテナ
      - Docker Engine
      - Hlem Chart
      - Elastic Cloud on kubernetes <--- NEW !!
  - 3rd
    - Amaxon Elastic Search xxxx
    - xxxx
  - 機能
    - ElasticSearchクラスタ(CRD)とKibana(CRD)のデプロイ
      - oc apply -f my-es-cluster.yaml
      - oc apply -f my-kibana.yaml
- ElasticSearch概要
  - javaベースで動く全文検索ソフトウェア
  - 複数ノードからなるクラスタ構成が可能
    - indexは分散配置(シャーディング)可能
    - レプリカによる高可用性
  - 可視化・ログ収集など周辺ソフトウェアが充実
    - App --> LogStach --> ElasticSearch --> Kibana
- ECKをAKSに入れてみる
  - kubectl applyでOperatorを入れて、その後各CRDをapplyする
- ECKをOCPに入れてみる
  - kubectlをocに変えただけでは入らなかったぞ
    - namespaceやserviceaccountを作ってpriviledge権限を付けておく必要があった
    - all-in-on.yamlを編集する必要がある
      - finallizerの追加
      - StatfulSetのspec
        - securityContext : priviledged : true
- OCPにOperatorを入れる際の(多分)一般的な注意点
  - OpenShift固有のSCCでハマる
  - OpenShift固有のRBACでハマる
    - RBAC定義(ClusterRole)
      - 明示的にfinalizerを追記する

## OperatorとOperator Lifecycle Manager(OLM)の概要とデモ

- Operatorのデモ
  - [OperatorHub.io | The registry for Kubernetes Operators](https://operatorhub.io/)
    - postgresqlを題材にしてみる
      - [OperatorHub.io | The registry for Kubernetes Operators](https://operatorhub.io/operator/postgresql)でできるもの
        - Primary x 1
        - Replica x n
        - Pgpool  x 1
        - Fail-over
        - バックアップ・リストア
    - デモ
      - postgres-operatorのデプロイ
      - CRDのデプロイ
      - postgres clusterのデプロイ
    - 一般的なOperatorの手順
      - Operatorはpod,serviceなどのk8sリソースを展開するので、
      - Operator podにk8sリソースへのアクセスを許可する必要がある
- OLMの概要とデモ
  - カタログ機能
    - Operator Manifest --> Cluster Catalog
    - Operator Manifest
      - Bundleと呼んだりする
      - CSV + CRD + Package
      - 1 CLusterServiceVersion(CSV)
        - Operator Container Imageを作るためのメタデータ
          - カタログ表示名
          - ロゴ
          - バージョン
          - Role/RoleBindings
          - CRD
          - Deployment(Operator Pod)
      - 2 Package
        - わかりづらいやつ
        - 用途毎やバージョン毎にchannelを構成する
      - 3 CRD
    - OLMの構成
        - 1 Catalog Operator
        - 2 OLM Operator
    - デモ
- Operator Hub
  - RedHat Operator
  - 認定 Operator
- まとめ
  - OLM
  - Operator Marketplace

## Solarflare Onload Kernel Bypass Solution for OpenShift/Kubernetes

- SOLARFLATE という会社だよ
  - [Onload® Application Acceleration Software | Solarflare](https://solarflare.com/onload/)という製品を出しているよ
- Why Containers ?
  - 
  - 
- Why Onload ?
  - User Space TCP Stack
  - 
- Use Case #1 Cloud Onload with Red Hat OpenShift
  - 
  - 
- Use Case #2 Cloud Onload with Kubernetes Calico
  - 
  - 

## Closing

katakodaで学べるぞ！
[OpenShift: Interactive Learning Portal](http://learn.openshift.com/)

次回MeetupではRookを掘り下げるぞ！
[OpenShift Meetup Tokyo #6 - connpass](https://openshift.connpass.com/event/139787/)
