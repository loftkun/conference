# React勉強会@福岡 vol.2

2019/06/05 Wed

GMOペパボ株式会社さんにて

ハッシュタグ [#react_fukuoka](https://twitter.com/search?q=%23react_fukuoka)

## バックエンドエンジニアから見たReact

ヤフー 杉永氏

- [バックエンドエンジニアから見たReact #react_fukuoka - Speaker Deck](https://speakerdeck.com/transnano/batukuendoenziniakarajian-tareact-number-react-fukuoka)
- java脳から理解しやすい
- component
- TypeScriptもかけるようになった
  - それは知らずにJSXで書いていた
  - TSXで触っていきたい
- SSR(Server Side Rendering)
- Hooks
- 社内ツール作った
  - markdown 2 confluence

## Progressive Hydrationについて

話題のanai氏
サイボウズ！
福岡初のエンジニア！
福岡でも採用しています！

- [Progressive Hydration #react_fukuoka - Seaker Deck](https://speakerdeck.com/pirosikick/progressive-hydration-number-react-fukuoka)
- HydrationのおさらいサーバサイドだけでReact使う	
  - ざっくりいうとSSR
  - CSR(Crient Side Rendering) Only
    - render
  - SSR + Hydration
    - ReactDomServer.renderTONodeStream
      - componentをHTML文字列として吐き出す
    - ReactDom.hydrate
      - DOMの構築をskipしてイベントハンドラの設定だけ行う
      - FCP
        - メトリクス(first content paint)
        - 早くなる
- progressive hydration
  - FCPは早くなるがTTI(ユーザ操作が可能となるまでの時間)は早くならない
  - Hydrationを段階的に行うことでTTIを短縮させる
  - Google I/O '19で紹介された
    - デモを用意している
    - リスト100件、スクロールにより画面に入ったタイミングでhydrationを動かしている
    - TTIが0.7秒高速に
    - コードを見てみよう
  - 導入すべきか？
    - リスクはほぼない
    - TTIが特別遅い場所で導入するのがよさそう
      - Auditsで簡単に計測できる

6/19 Google I/O '19 をまとめる会やります！

## サーバサイドだけでReact使う	

RelayHubの@anatooさん
『Webフロントエンドハイパフォーマンスチューニング』を書きました

[サーバサイドだけでReact使う / React as Template Engine - Speaker Deck](https://speakerdeck.com/anatoo/react-as-template-engine)

- いわゆるSSRの場合
- サーバサイドのみで使う場合
  - メリットあるの？
    - 十分ある
  - nodeで動かす場合
    - renderToStaticMarkup()を使う
  - React を テンプレートエンジンとして使っている
    - 普通のテンプレートエンジンより便利
      - リントや型チェックが効く
      - ビューの共通化が簡単
      - テスト用のライブラリが充実
      - エディタ・IDEの支援が受けられる
  - 普通のテンプレートエンジンより便利なんじゃね？

## GatsbyJSで自分のブログ作った話

ヌーラボ 川端さん

- ブログ持ってますか？
  - 作りました
- これまで、jugem, mixi, blogger, amebaを使ってきた
  - 続かない
- ポッドキャストと出会う
  - リーン、アジャイルが好きな2人が語る
  - 意識高すぎる神回
    - [#22 「Trello があるので眠れない」 | #omoiyarifm](https://lean-agile.fm/episode/22)
      - 週3本ブログ記事を書かなければ寝てはいけない
      - PVやはてブ数を集計
    - タスクは全てTrelloで管理
      - スラムダンク101話を2週間で見た
- デモ
  - 全部無料で使えます！
- netlify
  - 無料で使える静的サイトを公開できるサービス
    - Github/GitLabと連携してpushしたらデプロイされる
-  Gatsby
  - Reactで静的サイトを作れるライブラリ
- netlifyCMS
  - Headless CMS
    - 下書き=pull request

## React hooksを使ってみた

[React hooksを使ってみた - 岩本海童](https://scrapbox.io/odiak/React_hooks%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%A6%E3%81%BF%E3%81%9F)

- React hooksって何？
- 例
  - useState
  - useEffect
- メリット
  - 関数コンポーネントだけ書けば良くなる

## Angular使いがReactでアプリ組んだらこうなった

[Angular使いがReactでアプリ組んだらこうなった - Speaker Deck](https://speakerdeck.com/puku0x/angularshi-igareactdeapurizu-ndarakounatuta)


ベガ！

- 社内ツールをReactで組む
- TypeScript
- Abstraction
  - Service層
  - HttpClient層
- Separation of concerns
  - Business logic
  - State management
    - Entitiy Pattern
  - Components
- Lazy Loading
- Naming & structuring like Angular way

## Reactで釣果アプリ開発したお話

株式会社クアンド

- 釣りする人ーー？
- 弊社を代表する炎上プロジェクト
  - point
    - 70万人の会員をつなぐコミュニティのowned media
    - 釣りのビッグデータ
- なぜreactを使ったか？
  - サクッとアプリを構築したかった
  - ReactNativeへの移行も視野に入れて
- Redux使うことで進めやすかった
- 痒いところに手が届かない部分がある
- ReactNativeに移行したい
