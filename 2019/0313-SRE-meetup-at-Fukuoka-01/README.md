# SRE meetup at Fukuoka #1

2019/03/13 Wed

LINE Fukuoka株式会社さんにて

ハッシュタグ [#srefukuoka](https://twitter.com/search?q=%23srefukuoka)

![](https://pbs.twimg.com/media/D1h_gDsU0AAhR7v.jpg:large)

後ほどヤフーさんの提供で軽食が出ます！

## SRE入門＆チームで取り組んでいるSRE

LINE @matsumanaさん

- アンケ
  - 俺はSREだ
    - 4人
  - 会社にSREがいる
    - いなそう
  - 俺はSRE的な仕事をしている
    - 数人

SREとは？
- 範囲
  - DevOps
  - サービスを安定稼働
  - SLOとError budget
- 非常に重要なこと
  - SLO(Service Level Objectives)
    - The SIte Reliability Workbookが分かりやすかった
- SLIとSLO
  - Service Level Indicator
    - Availability(可用性)
      - リクエストの成功率
    - レイテンシ
    - Quality
      - フォールバックされたレスポンス
  - Service Level Objectives
    - SRE workbookでは必要以上に厳しいSLOを避けるために
      - 現状のパフォーマンスに基づいて設定することを勧めている
    - SLOが閾値を下回ったらユーザは不満を感じたり使うのをやめるかもしれない
    - SLO != SLA(Service Level Agreement)
      - SLAはユーザとサービス提供者の間の契約
- SLOを100%にするべきか？
  - No
    - そもそも使っているプラットフォームのSLOが100%ではない
- Error budget
  - Error budget = 100% - SLO
    - SLOから計算された許容できるエラーの割合
- SLOとError budgetを意思決定に使う
  - Error budgetを使い果たしそうになったら、新機能開発よりもサービスの品質改善に注力する、など
- SLOが有用で効果的であるためには
  - 全てのステークホルダーに同意してもらう必要がある
  - 継続的に見直して改善し続ける

- チームで取り組んでいるSRE
  - LINEのコンテンツ販売プラットフォーム
  - チーム編成
    - 東京 開発エンジニア10数人
    - 福岡 開発エンジニア10数人 + SRE１人
- PracticalなTopic
  - SLOとError budget
  - OnCall
  - ポストモーテム
  - DevOpts
- よりTechnicalなTopic
  - Monitoring
  - アプリケーションの運用
  - ミドルウェアの運用
    - mysql, mogodb, nginx, elasticsearch
  - キャパシティプランニング
    - 年末年始などのタイミングでリクエストが増えるので
    - 計画的にスケールアウトしたり、スケールアップしたり
  - Load test
- チームに入ってSREとしてやったことをご紹介
  - SLOをダッシュボードで可視化
    - SLI
      - Availability
      - Latency
    - SLO
      - 各マイクロサービスの現状に基づいてSLOを決定
      - 共有モニタにダッシュボードを表示
    - 課題
      - メトリクスが多い
      - ステークホルダとの合意
  - ElasticSearchのslow logモニタ

## SREとしての働き方

ヤフー @transnanoさん

- Agenda
  - Yahoo! Japanの紹介
  - Yahoo! JapanにおけるSRE

- Yahoo! Japanの紹介
  - 100を超えるサービス
  - Fintechに力を入れている
    - PayPay
  - 部署
    - [ヤフー塚穣×及川卓也対談　アジャイル／DevOpsと日本のITエンジニアの未来](https://www.atmarkit.co.jp/ait/articles/1808/28/news007.html)
  - チーム
    - 部署はSRE部、職種はプラットフォーム担当かな
- SRE
  - class SRE implements DevOpts
  - SREの担当領域
  - 完璧超人でなくチームワークで解決
    - スクラム
    - ペアプロ/モブプロ
    - スキルマップ
  - スクラム
    - 小さく回すのでPRも小さく明瞭
      - モブプロの場合、レビュー不要
    - SREとしての緊急対応にもマッチ
      - 小さく切られたアイテムの優先順位見直し
  - ペアプロ/モブプロ
    - ペアプログラミング≠ペアワーク
    - やってよかったこと
      - リリース自動化の属人化解消
      - 全員でやるとレビュー不要
    - 失敗したこと
      - 型を崩して我流でやる
        - 時間を無視
        - メンバーをシャッフルしてない
- SREした話
  - 技術選定
  - リリース回数増加
  - SRE輪読会による拠点内啓蒙

## 4ヶ月SREやって必要だった知識

ベガコーポレーション @kou__jpさん

LOWYAのARとかやってる会社です

必要だった知識
- インフラ設計
  - クラウド
  - ネットワーク
    - ルーティング, NAT, VPN
  - DNS, 証明書, ドメイン周り
  - サーバの以降
  - laC
  - コスト削減
- 監視
  - 外形監視
  - メトリクス
  - ログ
  - 自動復旧
  - 監視ツールの拡張
    - カスタムメトリクスを作ってDataDogに送る
  - 監視設定の効率化
- セキュリティ
  - NWレベル
  - ツールのアカウント・権限管理
  - WAF, UTMの導入
  - 脆弱性診断、脆弱性対応
- ツールの導入・連携
  - CI
    - CircleCI, TravisCI, shippable
  - 監視
    - Zabbix, etc
  - Slack
  - DataDog
  - Sentry

## イベント告知タイム

- impress鈴木さん
  - クラウドネイティブデイズ始動！
  - CLOUD NATIVE DAYS FUKUOKA 2019
    - プロモーションコード入れると1000円引きだぞ！

## 懇親会










