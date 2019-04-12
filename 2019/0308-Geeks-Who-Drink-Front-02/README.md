# Geeks Who Drink -自社プロダクト運用 Edition-

2019/03/08 Fri

株式会社ヌーラボさんにて

ハッシュタグ [#GWD_Nulab](https://twitter.com/search?q=%23GWD_Nulab)

![](https://pbs.twimg.com/media/D1ILQ5VU0AMBK8W.jpg:large)

![](https://pbs.twimg.com/media/D1IM147UYAAM8KQ.jpg)

## Atomic Design をコンポーネント設計の指標として取り入れた話

- 資料
  - [Atomic Design をコンポーネント設計の指標として取り入れた話](https://twitter.com/mya_ake/status/1103960372950663169)
  - [Atomic Design ベースのコンポーネント設計を考えてみた](https://twitter.com/mya_ake/status/1103975396637204481)
- Atmic Designとは
  - 知らない人ーーー？
    - 7割くらい
  - 化学分野の物資の組成をもとにする設計
  - 原典
    - Atomos
      - UIを最小化するための単位
    - Orgnisum
    - Templete
    - Pages
    - 実装方法は書いてない
- コンポーネント設計
  - Webは表示するだけのものでなくアプリケーション
- 実装の話
  - [nyatching](https://nyatching.com/)
    - 猫を預けたい人と預かりたい人をマッチング
  - うまくいった
    - コンポーネントの責務をしっかり分割できた
    - カタログ使って情報共有できた
    - Presenterで複雑さを生むところを分離できた
  - 失敗した
    - コンポーネントのカテゴリ移動
    - Organisms爆発

## SPA時代のステートマネジメント

- [資料](https://codepen.io/_fp/pen/YgWQpx?editors=0110%3C/a%3E%3Cbr/%3E)
- 和やかに進めたい
- Webアプリケーションの変遷
  - 太古(MPA)
    - CGI(掲示板,アクセスカウンター)
    - perl
    - HTML, Flash
  - 近世(MPA)
    - ショッピングカート
    - Webフレームワーク, REST
    - Ruby, PHP, Java, JavaScript
    - CSS, JQuery
  - これから(SPA)
    - GraphQL, BFF, Go, Scala, TypeScript, Flow
    - React, Angular, Vue
- Webアプリケーションにおけるステートマネジマントとは
  - ログイン
  - フォーム
  - トグル
  - 選択状態
  - 無限スクロール
- SPAのステートマネジマント
  - ステートは主にフロントエンドにある
  - 差分だけ更新される
  - Reduxのステートマネジメント

## Backlog における Kubernetes の取り組み

- 初出しの話です！
- [資料](https://twitter.com/nulabjp/status/1103976628294701057)
- Backlog
  - 国内・海外に8環境
  - サーバ台数は200
  - Issue, Wiki, Git, Fileなどの機能がある
  - サービス増で辛くならないように
    - Docker
    - AWS ECS
    - ステートレスな設計
- Kubernetes
  - yamlで定義
    - single source of truth
    - Infrastructure as Codeの極地
  - Cacooが使っている
  - EKS
    - Node の認証認可はAMI
    - Node のスケーリングにオートスケーリングを使える
    - eksctlというcliがあるが使わなかった
- BacklogにおけるEKSの構成管理
  - nginx
    - web
    - api
    - git
    - 上記から以下接続
      - MySQL
      - Redis
  - k8s追加
  - Terraformで管理
    - terraform applyコマンド
  - CloudFormation(CFn)
    - EKSのnode用のテンプレートがある
    - AMI変更してterraform applyコマンドで更新できる！
  - 質疑応答
    - yaml地獄についてツールか何か入れてる？
      - Kustomizeを入れている

## LT

### Nuxt.js

- [資料](https://twitter.com/_takeshi_24/status/1103987663667847173)
- あいみょんいいぞ
- Nuxt.js
  - Vue.jsのためのフレームワーク
  - TypeScriptをサポート
- JSX
  - テンプレートでなくJavaScriptの記法
  - 昔はロジックとデザインの分離って言ってたのに・・・
    - --> コンポーネント指向
      - 構造見た目振る舞いがセットになってる
    - yarn create nuxt-app my-project
      - ts未対応
      - nuxtを削除してnuxt-tsに置き換えていった

### お手軽scaffold

- [資料](https://twitter.com/karaagekeitaroo/status/1103986679600173057)
- scaffold
  - アプリケーションの雛形
  - Ruby on rails
  - Vue
    - Vue CLI
      - Generator
    - hygen
      - テンプレートはejs形式
        - テンプレート内でモジュールが使える！
          - fsモジュールとか

## 集合写真

![](https://pbs.twimg.com/media/D1I9L4wX0AAv2rI.jpg)