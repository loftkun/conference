# Serverless Meetup Fukuoka #4

2019/03/12 Tue

株式会社オルターブースさんにて

ハッシュタグ [#serverlessfukuoka](https://twitter.com/search?q=%23serverlessfukuoka)

![](https://pbs.twimg.com/media/D1c2blNV4AEmp-w.jpg)

## What’s happening with Serverless Framework, and it lives with AWS SAM.	

- 堀家 隆宏さん
- yaml --> transform --> CloudFormation(json)
- Provider
  - AWS
  - Azure
  - Kubeless
  - Oracle fn
  - CloudFlare
- Plugin System
  - Community Plubins
    - 200くらい公開されている
    - [serverless/plugins](https://github.com/serverless/plugins)
- `serverless deploy --stage prod`
- Serverless Application Repository
- Serverless Step Function Plugin
  - いろんな仕事をさせたいときに、ステップ実行的なことをしてくれる
  - ServeerLess API Gateway
  - Use Case
    - Realtime Raning System
      - ファッション系のWEBサイトのメンテナンスをしている
        - 記事のランキング
        - GoogleがリアルタイムAPIを出していて申請送ったらスルーされた
        - AWSのserverlessを使った
        - 記事IDに対してPVが登録されているのでそれを取得してフロントにランキングを見せている
      - PV以外のUse Caseにも使える
- [Serverless Dashboard For Atom](https://github.com/horike37/serverless-dashboard-for-atom)
  - エディタ上からできる
    - Deploy Functionボタンとか
    - Stage切り替えとか
- What is Cloud 2.0?
  - [Cloud 2.0: Code is no longer King — Serverless has dethroned it](https://medium.com/@PaulDJohnston/cloud-2-0-code-is-no-longer-king-serverless-has-dethroned-it-c6dc955db9d5)
  - Cloud 2.0っていうのは、もうコードも書くなという話
    - コードが少ない方が嬉しい
    - コードというのは責任
    - Serverlessアーキテクチャを作る上で考えないといけないのはコードの部分
    - 究極のServerlessアプリケーションというのはコードがないこと
    - よりコードをゼロに近づける
    - コードを書くならビジネスアイディアに直結したものを書くのが重要
    - マネージドサービスの可溶性を正しく理解し、より少ないコードにする


## アリババで荒ぶらナイと

- オルターブース 知念さん
- Alibaba Cloudとは
  - 質問 Alibaba Cloudを使ったことがある人はいますか？
    - いない
  - 19のグローバルリージョン
    - 東京リージョン
  - サービス
    - 中国 255
    - インターナショナル 101
    - 日本 55
  - Function Compute
    - イベント駆動型のコンピューティングサービス
    - 料金
      - 以下の掛け算
        - リクエスト料金
        - 実行時間料金
        - ネットワークトラフィック料金
    - メモリ
      - 128-1536MB
    - 対応言語
      - Python, Node, Java,,
    - 機能
      - トリガー
        - timer (UTC) 1分単位
        - リージョンによってつけるトリガーが違うので注意！
      - コード設定
        - コンソール画面から
          - zipアップロード
        - CLIツール
      - API
      - テンプレート19種類
        - コンソールで見れる
      - Invoke Function
        - 別のFunctionを呼び出せる(同期/非同期)
      - 監視
        - Cloud Monitor
          - Function毎にルール設定できる
          - 通知方法
            - email
            - DingTalkというアプリがある
- コンソールを見てみよう
  - 日本語
  - 中国語
    - 読めない
    - `人工知能`

- 質疑応答
  - 他のクラウドと比べて使い勝手は？
    - アーキを組む上では全体としてまだまだ
  - Alibaba Cloudをチョイスした理由は？
    - 趣味です
  


## Firecracker、下から見るか？上から見るか？

- うづらさん
- RubyKaigi 2019あります
- HACONIWA
  - container runtime
- Firecracker
- 下から
  - Amazonから発表されたマイクロVMか作成・管理するランタイム
  - kvmを利用している
  - ハイパーバイザ型
  - 特徴
    - 本物の仮想マシンを作るので隔離性が高い
    - Lambda, Fargateのバックエンドに採用されている
    - Apache 2.0 License
    - 導入
      - Linux 4.14+
        - Ubuntu bionic 4.15 などが必要
      - kvmが必要
        - AWS ベアメタルや、nested KVM可が必要
      - jailer
        - network namespaceを自分で作る必要がある
      - Kata Container
        - docker -> dockerd -> kata-container shim
          - `docker run -ti --runtime=kata-fc hello-world`
- 上から
  - kubernetesから使えないか？
    - kuberenetes - CRI(高レベルランタイム) - OCI(低レベルランタイム. runc, kata container, nabla)
  - どうやってk8sを入れる？
    - microk8sを使ってインストール＋カスタマイズ
      - ubuntuの上で動くsnapというパッケージ管理システムを使ってk8sを入れていく
  - デモ
- まとめ
  - もう使おうと思えば使える
    - 運用面、パフォーマンス改善はこれから
- CLOUDNATiVE DAYS FUKUOKA
- 福バネてす

## サーバーレスとRDBMSの相性の話（2019年3月版）

- AWS にしたに [Keisuke69](https://twitter.com/Keisuke69)さん
- [ブログ](https://www.keisuke69.net/)
- [ブログ](https://www.keisuke69.jp/)
  - キャンプ
    - こっちの方がアクセス数が多い
- Lambda Functionはウラ側はコンテナ
   - 1リクエスト1コンテナしか受けれない
- 一定時間、コンテナは起動しっぱなし(warm container)
- RDBMSと相性が悪い
  - 最大同時接続数
    - max connectionパラメタ
    - MySQLとかは上限値は数万
      - その値にしてまともに動くわけではない
      - DBエンジンが使うメモリ量＋接続毎のメモリ量×接続数
      - OS自体の上限
      - スケールアウトで対応するのではなく、スケールアップで対応することが多い
  - 各コンテナがDBにコネクションを貼ろうとする
    - Lambdaはステートレスなプラットフォームなのでコネクションプールを実現することが難しい
  - ダウンストリームとなるシステムなるシステムもスケールアウトするようなものでないと耐えきれない
  - DBは24時間上がりっぱなし、コストがかかる
  - RDBMSはAWSのVPCに置くことも多く、レイテンシの問題もある
- どうすればいいの？
  - Amazon DynamoDBを使う
    - コネクション数が増えることによるレイテンシが悪化することはない
    - NoSQLなのでRDBMSのように使うことはできない
  - RDBMSへの反映を非同期にする
    - Labmda --> DynamoDB -->(stream, 非同期) RDBMS
    - 投げつける系のアクセスを非同期にする
  - 同時実行数を制限する
    - re*Inventで発表された
      - 2017/12に発表された
        - アカウント単位で許可された同時実行数をファンクションに割り当てれる
   - Managing Concurrency
     - RDBMSを使いたいファンクションのみ同時実行数を
       - max connection以下にする
   - 痛みと付き合っていく
   - Aurora Serverlessがあるじゃない！
     - MySQL互換
     - Serverless用のAuroraではない！
     - Data API
       - HTTPSのエンドポイント
         - max connectionの問題がなくなっている
         - Secret Managerと連携
         - 制限はある
           - トランザションが使えない、など

## Knative Lambda Runtimeを試してみた

- [HideakiAoyagi](https://connpass.com/user/HideakiAoyagi/)さん
- Knative Lambda Runtime
  - KLR クリアー
  - Knative上で Lambda互換の関数実行環境を提供
  - Knativeって？
    - Kubernetewをベースとしたサーバレスプラットフォーム
    - 3つの主要コンポーネント
      - Build
        - 関数をビルド、コンテナイメージ化
      - Serving
        - リクエストに応じてコンテナを起動・スケーリング
      - Eventing
        - トリガーを実装
  - 前提
    - k8sクラスタ(GKE)
    - Istio
    - Knative
  - Step1
    - ビルドテンプレートをKnative上にデプロイ
    - tm deploy buildtemplate -f http*//raw.githubusercontent.com/tirggermesh/kanative-lambda-runtime/master/python-3.7/buildtemplate.yaml
  - Step2 関数をデプロイ
    - tm deploy servidce python-test -f https://〜

## 結合テストでNested Stackを使ったら非常に便利で、もしかしたらリリースにも使えるんじゃねって思った件

- [sinofseven](https://twitter.com/sinofseven)さん
- サーバレスってテスト難しい
  - Integration test
    - スタック分割
    - 分割したスタックどう管理しよう？
      - Nested Stackで分割したStack + αを管理
      - パラメータ管理しやすい

## サーバレスで新刊チェックボットを作ってみた	

- [kenichirou_kimura](https://connpass.com/user/kenichirou_kimura/)さん
- 新刊チェック
  - コミックダッシュ！
    - amazonをチェックして新刊候補リストを作ってくれる
  - API欲しいよね？
    - 作った
    - 新刊情報をS3に置くクローラ
    - S3から取得してjsonで返すAPI
    - そのうちGitHubに上げます






