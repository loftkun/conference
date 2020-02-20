# Cloud Native FUKUOKA #02

2019/08/08 Thu

TKP天神カンファレンスセンター：ルーム「B」さんにて

ハッシュタグ [#cnjp](https://twitter.com/search?q=%23cnjp)

## オープニング

- 昨日 Cloud Native Kansai #05 やりました！
- バズった記事 : ishida330さんのQiita
  - これでk8s勉強するのはやめた方がよいという議論がある・・
- 行動が重要
  - 本購入・ブログ・ツイート・LT・Slackに入る


## OSSによるCI/CD環境の構築

Rancher

Cheng (ちん)sann

- CDとは
- CI/CDのコンポーネント構成

- Rancher カタログ機能
  - GUIからOSSのCICDツールを簡単にデプロイできる
- Jenkins
  - Helm 公式のやつと
  - 比較的新しいOperatorのやつがある
- GitLab
- Rancher Pipeline
  - Rancherに統合されたCI/CD機能
  - 分岐制御はまだ弱い、シンプルなPipelineを作成する際にはおすすめ


## Traffic Management with Istio

私の発表

[Traffic Management with Istio ( with Demo )](https://speakerdeck.com/loftkun/traffic-management-with-istio-with-demo)

## CNDT/OSDT2019 振り返り(仮)

[#CNDT2019 / #OSDT2019 始めよう！ - Speaker Deck](https://speakerdeck.com/kitkatayama/number-osdt2019-shi-meyou)

## Alibaba Cloud発 OpenKruiseの紹介

- 中国市場は独占

- Alibaabのコンテナサービス
  - Elastic Container Instance
    - サーバーレスなコンテナ
  - Container Registory
    - ビルド後に脆弱性チェックができる
  - Container Service for kubernetes

- OpenKruiseとは
  -  ネイティブKubernetesの自動化エンジン
  - 2019/09にOSS化
- Advanced StatefulSet
  - PodUpdatePolicy
    - ReCreate
    - InPlaceIfPossible
    - InPlaceOnly
- BroadcstJob
  - CompletionPolicy
    - Jobを終了させるポリシー
      - Always
      - ActiveDeadlineSeconds
      - BackoffLImit
      - etc
- SidecarSet
  - Pod作成時に自動的にSidecarを配備する

## Cloud NativeとRancherでレガシーを近代化

- 特技は稟議申請/謝罪訪問
- 謝る時は順番が大事
- 働き方改革でPC強制シャットダウン
  - timezone変えたりしてたらばれそう

- 現代化は無理なので近代化

- レガシーとは何か？
  - VB 6.0
  - Active Server Pages
  - RPG/400
    - SQLが出てくる前にあったやつ

- オンプレのシステムをコンテナ化してSaaSとして提供できない？
  - モノシリックでシングルテナントなシステムをマイクロサービスに分解、さらにマルチテナント化するには？
  - 




