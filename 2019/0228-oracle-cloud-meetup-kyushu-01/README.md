# Oracle Cloud Meetup 九州 #1

2019/02/28 Thu

日本オラクル 九州オフィス さんにて

ハッシュタグ [#OraCloudKyushu](https://twitter.com/search?q=%23OraCloudKyushu)

![](https://pbs.twimg.com/media/D0fB_52UcAA6QIz.jpg)

## Oracle Cloudの使いどころ

- 全世界で使われ始めている
- 日本のリージョンももうすぐ来る！
- k8sを使ったコンテナ管理もある
  - クラウドネイティブにも力を入れている
- Oracle Databaseを使っている場合は他のクラウドよりも絶対に絶対に安い
- 強みは
  - データ分析
    - Autonomous Data Warehouse
      - ダウンしても自動リカバリー
      - すでにオンプレ・クラウドにシステムがあっても連携できる
- AWSと比較
  - 検証
    - Oracle Cloud
      - Object Strage
    - AWS RedShift
      - S3
  - 作成の簡単さ：どっちも簡単
    - Oracle Cloudの方が設定項目が少ない(6項目)、AWSは21項目
  - 設定の簡単さ：AWSに軍配、ただしスケーリングはOracleが簡単
    - Oracle Cloudは何かしらツールが必要
      - SQL Developerを利用してローカルから設定
        - Object StorageのURLの作り方が謎
        - JDK8の新しいバージョンが必要
      - スケーリングの設定は簡単だよ！
    - Redshiftは管理画面で設定できる
  - コスト
    - Oracle
      - 4CPU 2core
      - 5.03USD / 1.69USD ライセンスあれば安い
    - 構築のポイント
      - 2cpu以上がおすすめ
    - AWS
      - dc2.8xlarge : 32CPU 2.56TB 2Node
  - 検証データ
    - 首都圏から九州以外に向かった外国人
    - 東北に向かった外国人観光客数
  - SQL実行時間：Oracle速い
    - Oracle
      - 7.3 -> 3.5 -> 0.6 sec
    - AWS
      - 12  -> 1.4 -> 2.5 sec

## 『君の名は』

- 株式会社エバーライフさん
  - 主な事業：健康食品・医薬部外品の卸売通信販売
  - 「皇潤」でおなじみ
- 経緯
  - 復旧に8時間かかり社内SEの限界を感じる
    - 協力会社にお願いして調査してもらった
  - 止まらないシステムの勅命が下った
- 規模
  - 月24万アクセス
  - 月間売上5130万円
- 構成
  - LB
    - APサーバ CentOS6
    - mailサーバ
    - DBサーバ
      - Oracle
- 検討
  - DBはOracleを使用すること
  - 費用が安価であること
  - クラウドが候補に上がった
    - AWS, Azure
- Oracle Cloud ??????
  - パンフレット
    - アウトバウンド転送量
      - コスパがいい
        - 月10TBまで無料
          - 実質無料！
    - 24H365dayサポート
    - エンタープライズレベルのSLA
      - 性能に関しても出している
    - 金額
      - Oracle Database Cloud Service Enterprise Edition
        - 月額48000円
  - 「一刻も早くOracleさんを呼びなさい」
- リプレース構成
  - 東京リージョン予定
    - 2019/5 開始
  - 既存とほぼ同じ
    - LB
      - AP
      - DB
- 見積もり
  - 12.8万/月
- SEとして嬉しいのは基盤の運用をしなくて良いこと
- 「気づいたら君(Oracle Cloud)がいたんだ」


## Oracle Cloudを実際に使ってみた感想と他のクラウドベンダーとの違い

- 株式会社フルエナジーさん
  - Sillicon Graphics出身
  - 「松本昭史 cloud」でググれ(画像検索)
  - 東京都港区北青山
    - Oracleの4件隣
    - 技術者91％
  - 事業
    - SQLServer使っている会社のクラウドへの移行とか
    - VPN/専用線の接続支援
- 今日集まった人はどんな人？
  - 経営層/管理職
  - 技術職
    - 多め
  - 営業職
  - その他
    - ヘルプデスク
- つい最近までOracle Cloud使えん！と思っていた
  - 2015
  - 2016
- すごい！！
  - 2017
    - Oracle Cloud 国内DC
      - 画面サクサク
      - IaaSあり
      - DB時間課金
- やばい！！
  - 2018
    - ベアメタル
      - 52core
      - 700GBover mem
      - 斬新、使いやすい
        - Pricing
        - Universal Credits
        - 大きなサイズで買って使った分について安くできるようなプランがある
- 5月に案件を控えていて検証を進めている
- Azure
  - 2013
    - 機能少ない
    - ナレッジ少ない
    - まだ使えん
  - 2015
    - 本番運用きつい
    - Power Shell操作
    - 計画メンテ多い
    - 第1号案件で事故
  - 2016
    - 訳あり案件の運用に利用している
      - IP決めうちでやっているような案件
    - 安定稼働、そこそこ
    - Oracle動かすには高い(部分利用)
  - Azureならではのサービスは今後活用予定あり
- AWS
  - 2009
    - AWS US
    - 機能少ない
    - ナレッジ少ない
    - まだ使えん
  - 2014
    - c3.8xlargeを30台使って負荷テスト
      - オンプレのかなり大きなストレージ買うよりも高い
  - 2015
    - AWS Re:invent 4名参加
    - アンディージェシーとの質疑応答で
      - 日本のSIerは今後どうしたら良い？
        - 「AWSに客を運んで来てくれればいい」と言われショック
          - 一緒にやっていきましょう、とは言ってくれない
- Google
  - 2012
    - Google Apps利用
  - 2013
    - Google Platform本番利用
    - GCPの無料枠で社内システム継続稼働
    - GSuiteのAPI変更が多く、社内利用限定に
  - 2019
    - 改めて使ってみようか・・・
    - GCPに元Oracleのトップが入っているので期待している
- http://comparecloud.in/
- Oracle Database
  - 費用/性能/トレンド/ビジネスどれをとっても、これからすごい
- お客様にあったクラウドを提案しよう！
  - Oracle DB/Web Logic稼働するシステムはOracle Cloudに移行すべき
  - VDI環境刷新ならMicrosoft
  - パートナーを大事にするならMicorsoft, Oracle
  - 中国を攻めたいならAlibaba
- マルチクラウド構成
  - スペルチェックはOracle CloudにないのでそこはAzure
- マルチクラウド閉域網サービス


## 懇親会

ピザ🍕とお酒🍺




