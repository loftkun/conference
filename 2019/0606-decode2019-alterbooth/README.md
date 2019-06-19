# de:code2019 報告会 × オルターブース

2019/06/06 Thu

日本マイクロソフト 九州支店さんにて

ハッシュタグ [#alterbooth](https://twitter.com/search?q=%23alterbooth)

![](https://pbs.twimg.com/media/D8X5_YBUwAUkx1C.jpg:large)

## 全員参加の意義とは

小島さん！

- エンジニアだけでなくデザイナーや経理の人も含めて全員で行った！
- マイクロソフトのTOPは、lift & shift という手法は間違いだと言っている

## Application InsightsとCosmosDBまわり（仮）

- 1日目にケイスケ・ホンダが登場した
- Application Insights
  - Azure Monitorに統合されている
    - Insightsがとったメトリクスに基づくオートスケールやアラートの条件として利用可能
    - Azureポータルからリソース作るとよく勝手についてくる
      - 論理アプリケーション単位でまとめるのがオススメ
      - アプリケーションの設定はVisualStudioでやるのがオススメ
        - 主導やるとNugetの設定やら何やら面倒
  - ノイズ除去
    - ITelemetryProcessrorを継承したクラスを実装することでフィルタリング可能
- CosmosDB
  - いわゆるNoSQL
  - SDKのアップデート
    - OFFSET, LIMIT, DISTINCTが利用可能に
      - これがないとページングするの大変だよね

## ドキドキ・ライブコーディング！＠Blazor

- Teamsを使って東京からリモートでセッション！
- Blazor
  - C#でフロントエンド書ける
- ライブコーディング

## 僕が本当に欲しかったもの

- 適材適所なポジショニング

## 教育のためのマインクラフト

## de:code 超個人的まとめ

- 基調講演を除くと6カテゴリあるようだ
  - リテール
  - 生産性
  - セキュリティ
  - etc

## Azure Functionsとサーバーレス(仮)

- Alibaba Cloud MVP
- サーバレス
  - BaaS ( Backend as a Service) もあるんだよ
  - FaaS
    - イベントドリブン
    - イベントの分だけ課金
    - 処理が終了すれば破棄される
    - 完全マネージド
- Azure Functions 2.0
  - 2018/9に一般提供開始
  - ローカル環境で開発可能
    - スムーズに開発できる
  - 対応言語
    - C#, js, F#, Java8, TS
  - Trigger/BIndings
    - 12個
  - ホスティングプラン
  - 注目の機能
    - Durable Functions
      - これから多く使われそう
      - ステートフルなワークフローを作れる
      - 従来は Function -> Queue -> Function
      - これは Function -> Function
- Functions以外のサーバレスのコンポーネントもあるよ

## Azure DevOps+AKSによるコンテナパイプライン〜KEDAを添えて〜

- Azure DevOps
  - GitHubアカウントでサインインできるようになった
  - CI/CDをyamlでかけるようになった
  - pipelineでAKSなどのk8sへデプロイできるようになった
- AKS
  - KEDA
    - Kubernetes-based-Event Driven Autoscaling Component
  - Authenticated IP for Azure Kubernetes
  - Dev SpacesによるE2Eテストサポート
  - 西日本リージョン
- Demo
  - queueへのqueuingをトリガにpodがスケールするよ

## AI91セッション舞台裏

- デザインアーキテクト
- [ASCII.jp：松本典子の「Azure Logic Apps」超入門](https://ascii.jp/elem/000/001/647/1647224/)
- [noriji/decode2019: 2019/05/29-30 decode2019用の Azure Logic Apps サンプル集](https://github.com/noriji/decode2019)

## これから始める Bot Builder 開発のコツと舞台裏

[これから始める Bot Builder 開発のコツと舞台裏](https://www.slideshare.net/YutaMatsumura/bot-builder)

- decode MW01登壇しました
- BotBuilder v4 C# SDK チャットボットのユニットテスト
- レベル400 (上級者向け)
- Plan
- Build
- Test
- Publish
- Connect
- Evalate
- PHP Conference Fukuoka 2019 実行委員長してます！

## 決戦用MSセンチネル

- Microsoft Azure Sentinel
  - SIEM As a Service
    - Security Information and Event Management
  - SOAR
    - Security Orchestration Automation Response
    - セキュリティ運用の自動化
  - 監査ログには誰がどんな操作してるか全部記録されているぞ！

## 業務を便利にするためのTeams開発

- Teamsの良いなと思うこと(Slackと比較して)
- Slack
  - 将来的にメールに取って代わる可能性があるメッセージングアプリ
- Teams
  - ワークスペース
  - ストアにアプリが公開されている
    - タブ
    - ボット
    - etc
  - ないものは開発して追加できる
    - C#, Node.js
- Teams向けアプリ開発について簡単な紹介

## クロージング

じゃんけん大会！

- トートバック
- お掃除ロボット





