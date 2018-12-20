
# 緊急開催! Connect(); Japan 2018 福岡サテライト会場

https://fukuazu.connpass.com/event/112610/

オルターブースさんにて

ハッシュタグ [#MSFTConnect #fukuazu](https://twitter.com/search?q=%23MSFTConnect%20%23fukuazu)

![]()

## Visual Studio

`#nullable enable`

## .NET

Microsoft 井上さん

.NET Core3

WPF

dotnetコマンドで作成できる

`dotnet run`

`dotnet publish -r win10-x64 -c Release`

bin/Release/win10-x64/publishにできる

.NET Framework -> .NET Core すぐに移行する必要はないけど。

## IoT

IoTのMVPの方

[@matsujirushi12さん](https://twitter.com/matsujirushi12)

[Qiita](https://qiita.com/matsujirushi)

Device Simulator

Azure Cosmos DB

Maria DBもマネージドが出た

Azure DevOps Projects

- Azure IoT Support

VS Code

- Azure IoT Device WorkBench

## AI

株式会社キカガク 吉崎さん

Python

Jupyter Notebook

- 吉崎さんはこれで本書いた！

[Microsoft Azure Notebooks](https://notebooks.azure.com/)

- 大幅に更新された
- 無料！！！！！！
- ショートカットキーを覚えた方がいい
  - !つけるとOSのコマンドが使える
  - `!hostname`
- Extensionがたくさん入ってる
- GitHubと連携ボタンあり
  - notebookを持ってこれる
  - terminalからコマンド打ってもいい

VS Code Python Extension

- リファクタ
- Run Cell

Automated Machine Learning

- データセット
- 目標設定

Azure Cognitive Services

## Kubernetes+Java

寺田さん

### Serverless for Azure Kubernetes Services (AKS)

そもそもk8sのサーバってどこ？

k8sの構成図

Node, Pod,,,いたるところにサーバ

今回のサーバってどこ？

Knative Serving

- Podlessを実現

Osiris

- Podレベルでのスケール

Pod管理の課題

- VMの上で動いている
- VMにも限界
- VMにリソースがなければPodを増やせない
- PodのStatusがPending
- Pod部分を一生懸命頑張っってもダメで下側も頑張る必要がある

ノード(VM)もサーバ

- VMをスケールする機能はある(プレビュー中)
- VMは立ち上げるのに時間がかかる
- Podをスケールしたいのに対して時間がかかってしまう

Virtual Kubelet extending Kubernetes

- Microsoftだけのテクノロジーではなくなる
- CNCFに寄贈
- 今まではここのVMを増やしていた
- Azure Container Instanceというサービスを使う

これからKnative, Virtual Kubeletが熱くなる

通常のノードは仮想マシン
Virtual Kubeleteはコンテナインスタンス

デモ

- Podを30個にスケール
- -wでウォッチ
- めっちゃ早い、VMだとこうは行かない

### Cloud Native Application Bundles ( CNAB )

森山さん

Persistent Volume

Helmという仕組みがあるが、Azureのマネージドサービス、Teraform、Ansibleの呼び出しができない

CNAB(シーナブ)を発表

Duffle

- Helm ChartやDocker Imageが誰にSignされたか
- CNABで分かる
- アンインストールが簡単にできる
- Bundle


Phipy and Friends

- CNNFに寄贈
- 絵本
- 日本語に翻訳

## DevOps

Azure DevOps

- Boards
- Pipelines
- Test Plans
- Artifacts
- Lab Services
- Repos

GitHub + Azure Pipelines

デモ

- 最初は設定はWebUIで作った方がいい
- yamlにエクスポートできるのでカスタマイズできる

Azure DevOpsの素敵なところ

aldents-dev

Azure Repos

- 1つのプロジェクトに複数のリポジトリを紐付けれる

強力すぎるHostedAgent

リリースマネージメント

