# 【増枠しました！】#8 FukuokaJS『TypeScript』

2019/05/15 Wed

GMOペパボ株式会社さんにて

ハッシュタグ [#fukuokajs](https://twitter.com/search?q=%23fukuokajs)


## あいさつ

![](https://pbs.twimg.com/media/D6mcSYLUcAAqhBD.jpg:large)
![](https://pbs.twimg.com/media/D6mcR5ZU8AACdBM.jpg:large)

## Angular(あるいはNestJS)から始めるTypeScript	puku0x

ベガ！

- TypeScript触ったことある人ーーーーー？？？
  - ほとんどですね
- どうやって勉強していくか？
  - 実際に組もう
- Angular
  - 初心者でも始めやすい環境が揃っている
    - オフィシャルで型情報が提供されている
  - Type safety
    - `a : number`
      - 文字列が入るとコンパイルエラー
  - `interface`で型を定義できる
  - Decorator
    - @Component
    - @Directive
    - いろいろ使える
  - Generics
  - Dependency injection
  - RxJS
    - 非同期のイベントとかをストリーム(時系列)で配列っぽく扱える
      - filterとかmapとか使える
  - [Angular - Getting Started with Angular: Your First App](https://next.angular.io/getting-started)
- nest
  - [NestJS - A progressive Node.js web framework](https://nestjs.com/)


## TypeScriptの型について（仮）	ponday

ベガ！

- TypeScript = JavaScript + 型
- 型が書けるだけなんじゃねえの？と思ってませんか？
- とりあえずanyにしちゃう
  - TypeScriptの型システムを無視してしまう
    - 型検査ができない
    - 補完が効かない
- 型の表現力を高めるための仕組みが登場している
  - Static types for dynamically named properties
    - ```
      type User = {
        name : string,
        age  : number
      }
      ```
  - Mapped types
    - 型を変える、nullableかそうでないかとか
  - 型を条件に渡す
  - 定義できる型の幅が広がる
  - 汎用的なイディオムをまとめた組み込みの型関数は提供されている
    - Partial<T>
      - 型Tのプロパティをnullableにする
    - Reauired<T>
      - Partialの逆
    - Readonly<T>
      - 型Tのプロパティをreadonlyにする
    - Pick<T, K extends keyof T>
      - 型TからプロパティKを抜き出す
    - Exclude<T,U>
      - 型Uに代入可能な型Tを除去する
    - Extract
      - Excludeの逆
    - Parameters<T extends (...args: any[]) => any>
    - ReturnType<T extends (...args: any[]) => any>
      - 関数の戻り値の型が返る
    - 他にも色々

## TypeScriptでつくるNode.jsパッケージ	Yusuke Hirao

ディーゼロ 平尾さん！

- こんなの作ってます
  - jaco.js
  - markuplint

- 最低限のミニマムな
  - tsconfig.json
  - package.json
- tsconfig.json
- コードを書く前に決めておくこと
  - ディレクトリ構成
  - jsや型定義の出力先
    - libとかdestとか
    - npmで公開するファイル群
    - gitignoreしておいた方が良い
  - srcとlibは分けるのがおすすめ
  - src
    - gitで管理するがnpmには入れないのがおすすめ
  - jsのバージョン
    - es5
      - どんな環境でも動く
      - async/awaitやfor .. ofがレガシーコード変換される
    - es2017
      - Node.js v8.0.0以上なら動く
      - ブラウザで使う場合はbabelなどが必要になる
    - esnext
      - import.meta対応
  - モジュールシステム importとか
    - common.js
      - 現在の標準
    - esnext
      - import.meta対応
    - その他
  - 設定
    - yarn init
      - package.json
    - tsc --init
      - tsconfig.json
    - コンパイルコマンドを登録
      - package.json
    - 型定義ファイルを登録
- ビルド
  - `npm build`
- パブリッシュ
  - `touch .npmignore`
  - `npm publish`


## 休憩（10分）

## なぜTypeScriptでつくるWebAssemblyなのか	linyows

ペパボ！

- OCTOPASS
- DEWY
  - アプリ自身がCDする
- Fukuoka.go Organizer
  - 7/13 Go Conference 福岡

- WebAssemby
  - .wasmを作る方法
    - Rust or Go
      - 現実的でとても有力
  - TypeScript
    - cよりでかいがRustよりはサイズダウンする

- Fukuoka.tsを作りました

## コワクナイヨ TypeScript	どじねこ

- tsconfig.json
  - ts --> js 変換設定を書く
- babel7 から tsのトランスパイルが正式サポート
- unknown型
- 

## TypeScript × Azure × PWA	Shinichi Ueno

西部ガス情報システム 上野さん！

- PWA
- stack overflow
  - 言語のlovedランキングがある


## 懇親会