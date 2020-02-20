# Google I/O '19のWebをまとめる会

2019/06/19 Wed

株式会社ベガコーポレーションさんにて

ハッシュタグ [#mentaicojs](https://twitter.com/search?q=%23mentaicojs)


## What’s new in Angular

[puku@ng-fukuoka(@puku0x)さん | Twitter](https://twitter.com/puku0x)

- Survey of Large Enterprises
  - Why Angular?
    - The CLI
    - Opinionated Architecture
    - The Community
- New Conferences
  - ng-japan
    - 東京のgoogleにて開催予定
- 150万ユーザ突破

- Ivy
  - できること
    - Tree Shaking
    - Code Splitting
    - Progressive Hydration

## Securing Web Apps with Modern Platform Features」について

[すねこすり(@sunecosuri)さん | Twitter](https://twitter.com/sunecosuri)

ペパボ！

- 脆弱性攻撃手法
  - 35.6% XSS
  -  3.2% CSRF
- XSS対策
  - CSP : Content Security Policy
    - スクリプト実行をきめ細かく制御しXSSから防御
    - バグを修正するものではない、防御するための壁
    - レスポンスヘッダで定義
    - 某ホスティングサービス！のCSPの例、めっちゃながい・・・
  - Nonce-Based CSPの考え方
  - Trusted-types
    - DOM Based XSSという手法がある
    - サニタイズの処理をポリシーオブジェクトに集約できる
- CSRF対策
  - OriginとSiteの違いについて
    - same-origin
    - same-site

## 他の発表者の空気を読みながら被らないように全体的にまとめる話	

anaiさん

- What's new in JavaScript
- PWA on Desktop
  - 今後のPWA
    - ファイル操作について対応中
- Rendering on the Web
  - SPAのRenderignの手法と改善の話
  - Progressive Hydration <-- NEW!
    - この前React勉強会で話したぞ
- wasm : web assembly
- AMPについて
- Unlocking New Capabilities for the Web
- 印象に残ったところ
  - 会社ではもっと細かくやったぞ
  - Portals
    - 漫画ビューア
      - スムースに画面遷移できる
    - <portals>タグを書いてactivate関数を呼ぶだけらしい
    - まだバグが多い
      - Historyが消える
      - Portalsが入れ子になるとブラウザが落ちる
    - まだChromeのみ、他のブラウザはどうなるかわからない
      - moziilaのリポジトリのissueでportalsはどう？という会話がある
        - ネガティブな印象っぽいぞ
  - blueprint for performance success
    - 組織の同意を集める
    - ビジネスのゴールとRUMのメトリクスを紐づける
  - パフォーマンス計測、どんどん楽になっている
    - Lighthouse、どんどん機能が増えている
    - LightWallet, Plugin, Stack packs
  - wasm
    - js は deoptimizationがある
    - js はブラウザによってばらつきがある
    - wasmはどのブラウザでも安定している
    - wasm the right thing
      - 全てをwasmに寄せるのはいいアイデアとは言えない
        - デバッグが難しい
  - その他の感想
    - 国際会議なのでゆっくり喋ってくれる、聞き取りやすい
    - YouTubeの字幕がかなり正確
- QA
  - wasmの使い所
    - 画像処理
      - 4kの画像とか

## 休憩

## Modern Web Testing and Automation with Puppeteerについて

[mya-ake(@mya_ake)さん | Twitter](https://twitter.com/mya_ake)

[Google I/O 2019 の Puppeteer のセッション内容紹介と E2E テスト考察 - Slide - mya-ake.com](https://mya-ake.com/slides/modern-web-testing-and-automation-with-puppeteer)

- [GoogleChrome/puppeteer: Headless Chrome Node API](https://github.com/GoogleChrome/puppeteer)
  - パペチア
  - Chromeをnodeで操作するAPIを提供するライブラリ
  - スクショとかとれる
    - ビジュアルリグレッションテストができる
- デモ
- Firefoxでも使える(実験的)
  - 動かないAPIなども存在
- Runs Everywhere
  - Desctop, CI, ,,,
- 遅い理由
  - test(it)ごとにPuppeteerを起動する
    - テスト毎の環境をクリアにするため、正しい方法ではある
    - testごとにcontextを新規作成する手法があり、100倍くらい速くなるぞ
  - waitfor(1000)とかで待つ
    - waitforX()
      - waitforSelector()
      - waitforNavigator()
      - waitforRequest()
      - waitforResponse()
      - waitforFunction()
- パフォーマンステスト
  - メトリクス
  - トレース
- 複数プロセス
- E2Eテストで何をテストするか

## Puppeteerで使われていないCSSを消す

anaiさん

おめでとうございます！

- 最近やっている仕事
  - 巨大なCSSのstyled-componets化
    - 1万行
    - bootstrapやawosomeを上書きしている
    - どう戦えばいいかわからん
- Puppeteer
  - パペチア
  - JS・CSSのカバレッジが取れるらしい
    - この機能を使えばよいのでは？
- page.coverage.start/stopCSSCoverage()
- puppeteer-to-istanbulでnycが処理可能なフォーマットに変換
- 1万行あって、カバレッジ7.27%・・・！
  - 手で消すのはつらい
    - .nyc_output/out.jsonの情報を使えばよさそう
      - 消せた！
      - 1万行が800行に！
- 検証
  - 消す前/後のスクショの画像差分を出すようにしたぞ！
  - puppeteer便利！
- QA
  - みなさん画面のE2Eテストどうしてんの？
     - `Visaul Regression`という分野
       - [reg-viz/reg-suit: Visual Regression Testing tool](https://github.com/reg-viz/reg-suit)
         - 画像の差分を検出できるらしい
       - masterブランチでスクショ撮っておいて開発用branchのと比較する

- サイボウズでの報告会のスライド紹介
  - UXに最も効果があるのはロード時間である
  - Firebase Web Performance Monitoring
  - lazy load
    - これまではjsのライブラリとかで実現してたけどブラウザでサポートするようになる
  - Project Fugu
  - Web Share
  - Promise.allSettled
  - [Squoosh](https://squoosh.app/)
  - PWAのインストールボタンが表示できるようになる