
# Serverless Meetup Fukuoka #3

https://serverless.connpass.com/event/102585/

Twitter [#serverlessfukuoka](https://twitter.com/search?q=%23serverlessfukuoka)

2018/11/16(金)
さくらインターネット福岡オフィス

# Azure

- Cosmos DB
  - NoSQL
- Event Grid
  - イベントを拾ってFunction, Logic に投げれる
  - 監視ができる
- Logic Apps
  - サーバレスワークフローを構築できる
- Stream Analytics
  - リアルタイム分析
- Bot Service
  - ボットを作れる
    - SMS, Skype, Line
- BLOB Storage

# ETL

- S3に置かれたデータを可視化したい
  - Extract   : 抽出
  - Transform : 加工
  - Load      : 読み込み
- AWS Glueを使った
  - データをParquet形式にして可視化
    - https://parquet.apache.org/

# 各社のFaaSを比較

- Serverless Compute Manifestoというものがある( o はタイポではない)
  - https://medium.com/@denismakogon/demystifying-serverless-compute-manifesto-ee07a3c2565c
- AWS Lambda
- Azure Function
- GCP Cloud Functions

- PostManで初回を計測
- ab コマンドで10接続で100リクエスト
  - 一回実行後に再度実行

# Alexa SDK

- Alexa SDK

# Scalable Serverless DataReceiver

- API Gateway - lambda ではなく、
- API Gateway - Queue - lambdaでポーリングにした

# コンテナベースサーバーレスプラットフォーム「Knative」はServerlessなのか？

- Knative
  - kubernetesをベースとしたサーバレスプラットフォーム
  - 一定時間リクエス トが途絶えるとコンテナ数が0になる
  - kafkaなどのメッセージングシステムと連携してコンテナを起動
  - Github -> DockerHub -> Knative
  - GKE Serverless add-on がKnativeと同時発表されたαプレビュー中で、マネージドなKnativeになる？
  - Knativeが目指す世界
    - @IT Googleのウルス・ヘルツル氏に聞いた、「IstioやKnativeで目指すのはクラウドのアンロックイン」
      - http://www.atmarkit.co.jp/ait/articles/1808/28/news036.html
  
# Serverlessconf Tokyo 2018に行ってきた

- サービスマップ  Epsagon
- Portable Functions
  - VS Codeでブレークポイント貼って動かせる
- Durable Functions
  - 関数オーケストレーション