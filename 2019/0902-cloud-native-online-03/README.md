# Cloud Native Online #03

2019/09/02 Mon

Zoom（Web会議）

ハッシュタグ [#cnjp](https://twitter.com/search?q=%23cnjp)

## Opening

[ShindoY@Rancher](https://twitter.com/shindoy)さんより

- 参加場所アンケート
  - チャットを活用
    - 日本全国から参加！
- Tweetもよろしく
  - ハッシュタグ [#cnjp](https://twitter.com/search?q=%23cnjp)
- Qiita/はてな/note/Togetterなどでまとめてね！
- GWに各地回りました
  - また秋口にかけて全国回ります！

## Talk 1 エンタープライズKubernetesを再定義する - Red Hat OpenShift 4 by 北山晋吾 (spchildren) 

- 一般的にkubernetesってこれからどうなっていくの？
- RedHatはCoreOS社を買収しOpenShiftの機能を大きく広げた
- CoreOS社
  - CoreOS
    - コンテナ専用OS
  - Tectonic
    - パブリッククラウド上にk8sを展開できる
    - Rancherみたいなもの
- 今日は自動管理にフォーカスして紹介します
- k8sを本番環境に載せるときにモニタリングなどが必要となってくる
  - VMレベルなら名前つけて管理
  - コンテナレベルだとそうはいかない
  - オペレーションコストが大きくなってくる
  - statefull
    - コンテナ化するとしんどい
    - 障害復旧がしんどい
  - stateless
    - コンテナ化して管理できる
- statefullはコンテナかに向かない、その流れが大きく変わってきている
  - Operator
    - 運用の知見をコード化
    - Observation -> Analysis -> Action
    - statefullアプリケーションに対してはActionが変わってくる
      - DBの場合、master or slaveで変わる
        - 死んだmasterを切り離す
        - slaveをmasterに昇格させる
        - 死んだmasterを復旧させる
          - リストアしてからクラスタにjoinさせる
    - k8sの2つの機能を利用して実装されている
      - CRD(Custom Resource Definition)
      - Custom Controller
        - CRDを監視して適切なリソース状態を維持する
  - 例 Prometheus Operator
    - CRD for Monitoring
      - Prometheusというリソースが定義されている
      - CRDの中にService Monitorを書くこともできる
        - k8sのServiceを指し示していて管理できる
    - CRD for Alerting
- Operator Hub
- Operator Lifecycle Manager
  - Operatorは単独で動いているのではなくLifecycle Managerにより管理されている
  - [OpenShift: Interactive Learning Portal](https://learn.openshift.com/operatorframework/)

## Talk 2 Kubernetes(k8s)でシステム運用する際の シークレット情報の管理について調べてみた (@hiropin_pon_pan) 

- AWS EKS利用前提のお話
- シークレット情報をセキュアに管理する方法を列挙しました
- Kubesec
  - 暗号化したSecretをgitにpushしておく、CI/CDでデプロイ時に復号化する
- Kubernetes-external-secretes
  - `kind: ExternalSecret`をkubectl applyすると値を取得してくれる
- Sealed-Secrets
  - `kind: SealedSecret`をkubectl applyすると値を取得してくれる
- HashiCorp社 vault
  - vaultサーバを立てておいてkey/valueを取得する
  - init container
    - image : valut (vault-agent-authコンテナ)が用意されている
  - init container / sidecar 経由でapp コンテナでkey/valueが取得できる
- AWS Secret Manager
- AWS Parameter Store

## LT - どうやって始める？?クラウドネイティブの第一歩 (@kitkatayama) 

[どうやって始める？クラウドネイティブの第一歩 / how-to-start-cloud-journey - Speaker Deck](https://speakerdeck.com/kitkatayama/how-to-start-cloud-journey)

- 前職でクラウドの運用やってたよ！
- クラウドネイティブってなんやねん
  - CNCFから出ているぞ
- まんがではじめるkubernetes
- k8s公式チュートリアル
  - minikube
- わりとゴツいゴツいKubernetesハンズオン
- kubernetes 完全ガイド
　
## Talk 3 Cloud Native をやっていくにはどう学んでいくかをみんなで考えてみる (@yassan168) 

[Cloud Native をやっていくにはどう学んでいくかをみんなで考えてみる](https://www.slideshare.net/yasukazunagatomi/cnjponline03/yasukazunagatomi/cnjponline03)

- スライド上にコメントが流れるよ
  - https://comets.nabettu.com/?id=cnjp
- TrailMap
- 書籍
- 勉強会
- イベントに参加する
- 11/27,28 Cloud Native Days Kansai
- おすすめは「発表する」こと

## Closing Cloud Native の裾野を広げる DX (@手羽先) 

- Cloud Nativeの裾野を広げるにはどうしたらいいんだろう
  - DXも始めていきたい
    - 9/6 名古屋 DX Japan Meetup #DXJP

[ShindoY@Rancher](https://twitter.com/shindoy)さんより
- 行動が大事
  - 本購入、ブログ、ツイート、LT、Slackに入る、Organizeする
  - ツイートすると流量でLV感が分かる