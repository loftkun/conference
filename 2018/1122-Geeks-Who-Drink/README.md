# Geeks Who Drink -自社プロダクト運用 Edition-

2018/11/22 Thu

https://nulab.connpass.com/event/105113/

株式会社ヌーラボさんにて

ハッシュタグ [#GWD_Nulab](https://twitter.com/search?q=%23GWD_Nulab)

![ヌーラボさん](https://pbs.twimg.com/media/DsmXDRuU8AAMVQ6.jpg "ヌーラボさん")

## CacooはなぜKubernetesによるmicroservicesへの道を選んだのか？

- サービスをどこで区切るか
- コード/yamlの冗長性
- DBをまたいだトランザクション
- モニタリング
  - Prometheus, Graphana

- 継続的な開発がしやすくなった
- 部分的な変更

まだまだ課題はある

### 質問タイム

- logの収集は？
  - fulentd
- DBを跨いだトランザクション
  - 全て解決してるわけではない
  - ゼロから作るのではないためしがらみもある
- マイクロサービス間はprotocol buffer使っている点
  - 型の不一致の解決法は
    - 追加された分動くような感じになっている
    - 削除はしてない

## Backlog における SRE の事例 〜プロダクトの成長のために SRE はなにをすべきか〜

BacklogチームのSRE担当さん
SRE Lounge #5で発表した資料を元にしている
sre-lounge.compass.com

### 製品

- backlog
  - プロジェクト管理
- cacoo
- typetalk

### 組織が大きくなると全員が開発と運用を兼務するのは辛い

backlogは
コンポーネントごとに複数チームがある

- 開発チーム
- SREチーム
- サポートチーム

AWSで運用している

#### SREの定義

Optsの職種
運用業務と改善のエンジニアリング

業務＋αを期待されることが多い
インフラとアプリ両方の理解が必要

#### DevとOpsの分離が引き起こす問題

平均復旧時間(MTTR)の増加

#### インフラ寄り、改善寄りのSRE

チームをまたいだ情報共有の役割を担う
運用が回り始めた、運用ミスが減った
SREの採用を強化中

## 全世界から爆速で使えるTypetalkを目指して〜キャッシュしない CDN による API 高速化 〜

Typetalkのインフラエンジニア

技術書毎月１冊手当がある！

### Typetalk

チームのためのビジネスチャットツール

AWS使ってる

お手頃価格

#### 抱えていた課題

ユーザの場所(国/地域)により応答速度が差がある

改善により440ms -> 180ms

特にモバイルの体感向上

低コストで実現

#### CDN

オリジンからキャッシュする
静的ファイルの配信に適している
ユーザから最も近いエッジに誘導される

キャッシュしてはいけないので、動的な部分には使えないというイメージがあるが・・・

### キャッシュしないCDNによるAPI高速化

動的な部分にたいして適用できる

AWS CloudFront
全部オリジンに転送してキャッシュしないように設定している

注意

- キャッシュ設定を誤るとセキュリティ事故につながる
  - キャッシュしてはいけないものをキャッシュすると
    - 他のユーザのマイページが見えてしまったり
- WebSocketに対応していない場合がある
  - WebSocketはCDNを介さない工夫をした
  - CloudFrontはWebSocketに対応した！昨日！！
- L4情報を用いたクライアント制御に影響が出る
  - IP制限機能とか実装してる場合は注意
  - nginxの設定を工夫した
    - X-Forwarded-Forヘッダを使う
    - ALB/CloudFrontのエッジIPを信頼できるプロキシに登録した
      - CloudFrontのヘッジIPは変化するので注意
        - SNSで変更通知を受け取れるのでLambdaでJenkinsのjob(Ansible)起動してる

### 今後改善したいこと

Autoscalingやk8s導入したい

エンジニア募集中！

- Scala
- DevOps

## LT

### LINE FukuokaのSREの方

https://twitter.com/matsumana/status/1065574049512742918

microservicesについて

デモ
- Prometheusの画面
- Zippkinの画面
- ソースコードを公開してる
- ブログで紹介してます

### ヌーラボ iOSエンジニアの方

Scala福岡2019

1/19 11:00-20:00

センター試験と被ってる

### Backlog リデザインチーム Jalalさん

英語によるLT！！

State managementの話

React-tooling

学習コスト低いよ
ホットローディングできるよ





