# Google Cloud Next 2019 Extended in Fukuoka

2019/04/24 Wed

株式会社グルーヴノーツさんにて

ハッシュタグ [#gcpug福岡](https://twitter.com/search?q=%23gcpug福岡)

![](https://pbs.twimg.com/media/D46RZfXU4AAwDaV.jpg:large)
![](https://pbs.twimg.com/media/D46RZfXUIAI0t-_.jpg:large)

## セッション1:Data Analytics関連の紹介

カホエンタープライズ 大隈 さん

- アビスパ福岡にてシステム担当していた！
  - Twitter, Facebookの中の人をやっていたよ！
  - どんたくでマスコットの中の人もやったよ！

- Agenda
  - Google Cloude Next 2019について
  - 受講したセッション
  - Data Analytics関連の紹介

- Google Cloude Next 2019について
  - 来場者30000+
- 受講したセッション
  - 3days
    - 1 Openning Keynote + 4セッション
    - 2 Product Innovation Keynote + 4セッション
    - 3 3セッション
- Day 1
  - Anthosの発表
    - 大隈さんは"アントス"と発音されているぞ！
    - ハイブリッドクラウドの推進
  - Big Query
- Day 2
  - 新プロダクトの発表
    - Cloud SQLがMicrosoft SQL Serverをサポート
    - Active Directoryのマネージサービス
    - Big Queryのベストプラクティス
      - おすすめ！
- Day 3
  - Modern Data ware hous Big Query
- Google Cloud Next のページ
  - セッションでフィルタかけて見ることができるぞ！

- Data Analytics関連の紹介
  - エンジニアリングというところにパワーをさかずに、
    - クエリ書いて仕事したい
    - 構造化されたデータを2, 3クリックでモデルを適用して機械学習行えるような
  - Cloud Data Fusion
    - 各データソースからBig Queryにデータを突っ込む
      - GUIでデータパイプラインを作れる
      - フルマネージドs
  - Big Query BI Engine
    - Big Queryのデータをin memoryにぶっこんでアクセス
      - ほぼ瞬時に可視化、分析、操作可能
  - Connected sheets
    - スプレッドシートにBig Queryのデータを
      - 100万行だろうが、億に近いデータを扱える
  - Auto ML
  - Data catalog
  - Saas application connectors
    - 100種類を超えるアプリに対してconnnectorが提供される

### デモ
- Cloud Data Fusion
  - Cloud Storage
    - 福岡市のインフルエンザ報告数データセットを突っ込んでいる
  - Data Fusion
    - Dateset
      - Wrangler
        - ソースを選べる
        - カラム名変えたり、不要な列を削除したり、型を変えたりできる、置換もできる(空セルを0.0にするとか)
          - この辺はGUIで操作でき、それらの手続きのコマンドも生成される
    - BigQuery
    - Data Pipeline
  - デプロイ、runするとBigQueryに突っ込まれる
- Big Query BI Engine
  - 2019/07まで無料で使える
  - Q3から課金予定
  - サンフランシスコのシェアサイクルの1億レコードを使ってみた
  - 比較
    - BIエンジンありとなしで、集計期間を変えて見ると、ありは瞬時に結果が表示されるぞ！

### まとめ/質疑応答


## セッション2:What's New in Serverless Compute?

メルペイ！

[しんめたる@sinmetal](https://twitter.com/sinmetal?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor)さん

- 同名のセッション(YouTubeにある)をまとめた発表です
- 英語はできないのでホテルで字幕付きのYouTubeの発表を見ていました
  - [What's New in Serverless Compute? (Cloud Next '19)](https://www.youtube.com/watch?v=Zfnhg1wneiA&feature=youtu.be)
- Stadiaの展示！

- Google App Engine Standard
  - App Engine SDKがサポート外となる
  - GCPの中でHTTPを受け取る入り口としてのシンプルなポジションへの以降が明確となっている
  - (私 もう過去の技術かなあ)
- Google Cloud Functions
  - `--vpc-connector`
- Google Cloud run
  - HTTP Handlerを持ったContaier ImageをDeployすれば
  - Requestが来た時にContainerを立ち上げてくれるサービス
  - (私 感覚的にはFaaSだな、てかServerlessのセッションだからなこれ)
  - Cloud run と Cloud run on GKE(Knativeベース)がある
  - 制限
    - Max 2GB
    - 80 conncurrency(同時に処理するリクエスト数)
    - 最長処理時間15min
    - 今はVPCと接続できない
- Google Cloud Tasks, Cloud Pub/Sub, Scheduler
  - Native GCP Auth (IAM) on HTTP
    - PubSub, TasksからのRequestにAuthorization Headerを付けてくれる


