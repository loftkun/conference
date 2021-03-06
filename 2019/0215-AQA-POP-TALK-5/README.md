# 【満員御礼】AQA POP TALK #5 みんなQAとか自動化どうやってるのスペシャル

2019/02/15 Fri

メルカリ 福岡オフィス さんにて

ハッシュタグ [#aqapop](https://twitter.com/search?q=%23aqapop)

![](https://pbs.twimg.com/media/DzcQgAUUcAIIbdy.jpg)

## テスト設計実践事例

20分ほど遅刻して到着したのでほとんど聞けず

## 福岡開発立ち上げQAメンバーが語る「メルカリQAのはじめかた」

- メルチャリは福岡にしかない
- 最近メルペイをリリースした
- 福岡UXチーム
  - Engineer
  - 分析チーム
  - AQA
    - Automation & QA Group
      - Automationメンバー
      - QAメンバー

### QAの始め方

- 10月にjoin
- 福岡で1人目
- 他メンバーは東京
- キックオフ
  - 10枚化プロジェクト
    - 出品時にUPできる画像を4枚から10枚に増やす
  - 見積もる
  - QA準備
    - テスト見積もり
    - テスト計画
    - テストスケジュール
- メルカリアプリの構成
  - Client
    - iOS
    - Android
  - Web
    - Frontend
    - Backend
  - CSツール
- リリースは15分毎！！！！

## メルカリにおける自動化テストのこれまでとこれから 〜 WEB ＆ APP 〜

AQAの方

- UIテスト
  - 自動化について話します
- これまで
  - tech.mercari.com/entry 参照
- 今
  - Webの重要度が高まっている
- AppとWebの品質
  - App
    - バージョンが残る
    - しっかり期間をかけて開発してからリリース
    - QAフェーズでUIテスト
      - QAのためのUIテスト
  - Web
    - 1day毎にリリース
      - 切り戻し可
    - 開発プロセスの中でUIテストを回す
      - デベロッパー寄りのUIテスト
- 全員自動化
  - 全員が自動テストに関わっていく
    - Turnip ターニップ
- UIテスト戦略
  - 目指している世界
    - デベロッパーにUIテストを自分ごととして捉えてもらう
    - 模索中の話もします
    - 求められている機能を実現する
      - 使われる機能を作る
        - Webチームから求められていること
        - QAチームから求められていること
    - 使ってもらうハードルを下げる
      - 技術選定
        - デベロッパーと同じ言語
          - TypeScript
          - node.jsの自動化ツール
            - 10個以上あり、カオス
        - Cypress
          - クロスブラウザの観点が❌
        - TestCafe
          - 次点
        - WebdriverIO
          - 拡張性○
          - 採用
        - Slenium
    - 見てもらうことを習慣化する
      - CICD
        - PR毎にUIテストを実施
        - デプロイパイプラインにUIテスト組み込む
        - 今後起きうる問題
          - ケース数が増えるとテスト時間が増える
            - ヒント
              - Seleniumカンファレンス
                - Scaling Selenium to infinity
    - 使ってもらう人を増やす
      - 教育
    - +α機能の実現
      - 全ての差分を検知することは現実的でない
        - assertionを全ての要素にかけることは現実的でない
          - 現実的にはスクリーンショットを撮って差分を検出する
            - Online Serviceがいくつかある
              - データの初期化ができるかどうかで分けられる
                - できるものは前と変わらないものが維持できる
                  - ほとんどのツールがOK
              - できないものはApplitoolsが適している
          - Applitools
            - AIによる差分の抽出
            - 対象のエリアを囲むと中に差分があれば検出してくれる
- 自動化は始まったばかり、今後に乞うご期待

## 
    







