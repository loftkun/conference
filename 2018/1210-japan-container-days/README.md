
# JapanContainerDays v18.12 報告会＠福岡

https://connpass.com/event/110115/

GMOペパボさんにて

ハッシュタグ [#JKD報告会](https://twitter.com/search?q=%23JKD%E5%A0%B1%E5%91%8A%E4%BC%9A)

![](https://pbs.twimg.com/media/DuDD87hU4AEmLMr.jpg)

## JKD オーガナイザー 鈴木教之さん＠インプレス

Cloud Native Days Fukuoka 2019 開催決定！！！

## のむらさん

dockerに限らず仮想化技術はiptablesを駆使してる

これからはipvs proxyがくるぞ


### セキュリティ


### CRIU by うづらさんs

`docker checkpoint`

### コンテナ技術の今後

- Knative
- Rio(Rancher)
- Operator

### まとめ

snapコマンドが便利

## うづらさん

Using CRIU to make boot fast

コンテナランタイム

Deep Dive

Firecrackerってどうなの？

## オルターブース 加藤さん

### k8s

Immutable Infrastructure

コンテナは停止しやすく作る

k8sクラスタ自体も使い捨て

- k8sのクラスタ自体は極力簡単にする

yaml設定は適切に

- CPU, memory
- 1つのコンテナがホストのリソースを食いつぶつってこともあり得るので

k8sだけが全てでない、他の選択肢も考慮する
サーバレスを使うとか

### NoOps

運用の「嬉しくない」をなくす

Defensive NoOps

- 自動化を進める

Offensive NoOps

- 構造的にOps不要なシステムにする

Istio

Knative

- 開発者がyamlを意識せずにデプロイできる

Istioの目指すセキュリティゴール

- Zero-trust network

The Network is the computer. を見据える

NoOps = No Boundary

## LT

### rconの全て

rcon of the year

cgroup

- cpu.cfs_period_us
  - CPUリソースの割り当て間隔マイクロ秒

- cpu.cfs_quota_us
  - 　

Usage : rcon

こういうの便利

- バッチ処理が重い
  - rconでCPU使用率を制限

最近やったやつ

- ウイルススキャン(clamdscan)が重い
  - rconで`--user root --cpu 30 --command clamdscan`

実は便利なのはmruby-rcon

rcon - mruby-rcon - make cgroup - system - delete cgroup

是非使って！

### クラウドネイティブなビルド

CNCFによるクラウドネイティブの定義

ベンダーに中立なプロダクト

OCIによる標準化

- Container Runtime Specification
- Container Runtime Image Specification

CRI : Container Runtime Interface


#### イメージのビルドどうしてますか？

BuildPackとは

OCIに準拠したイメージを作れる

Herokuが作った

Dockerに依存しないイメージを作れる(オープンである！)

dockerfile記法に縛られない

システムとアプリの分離ができる

- Heroku v1, v2a作った
- CNCF v2b 作った
- OCI v3 作った

## プレゼントコーナー

- ZOZO スーツ
- IBM スマホレンズ
  - 当たった！![](https://pbs.twimg.com/media/DuDgrciV4AEvbJd.jpg)


