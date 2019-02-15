# LINE Developer Meetup #50

2019/02/13 Wed

LINE Fukuoka株式会社 さんにて

ハッシュタグ [#LINE_DM](https://twitter.com/search?q=%23LINE_DM)

![](https://pbs.twimg.com/media/DzRyWPSVYAAgd-H.jpg)

![](https://pbs.twimg.com/media/DzRyW83U8AI7Hbs.jpg)

## LINEでのモバイルアプリ開発

- Client App
- Teams
- Development
- Challenges
- Future

### Client App

- 日本、タイ、インドネシアでよく使われている
- 50億メッセージ/day (peek)
- WebViewをよく使っている
  - Lineマンガ、チケット、ショッピングとか
- 規模感
  - iOS Client
    - Obj-c 50%
    - Swift 50%
    - total 1.3Mline
    - 100人くらいで開発
    - 1k PRmerge/month
  - Android
    - Java 70%
    - Kotlin 30%
    - 1.5M line
    - 1k PRmerge/month

### Teems

- チーム構成
  - Tokyo, Seoul, Taipei, Fukuoka, Hanoi, Kyoto
  - Cross Functional Teem
- コミュニケーション
  - LINE
  - Slack
  - LINE WORKS
  - Confuluence
  - JIRA
  - Zeplin( Visual Design )
  - GitHub Enterprise
- Language
  - 共通言語はEnglish
  - 必要に応じてミーティングなどで同時通訳をお願いできる

### Development

- CI
  - Jenkins
  - Circle CI
  - SwiftLint, Danger, ktlint, SOnarQUbe, JaCoCo, PR Comment Bot, Submodules checker, gradle-versions-plugin
- Libraries
  - ReativeX
  - glide
  - Yoga (facebookのレイアウトエンジン)
  - Reactive Swift
  - Firebase
  - Robolectiric
    - Android, Unitテスト支援
- Branch Management
  - Simillar to GitLab flow
    - GitHub flow + release ブランチ
  - ブランチ
    - Trunk ( main )
    - Topic
    - Release ( bug fixをcommitする。最終的にTrunkにマージする )
  - Auto Merger
    - Relaseブランチでbug fixをたくさん行うが、Trunkにマージされずconflictに苦労する背景があった
- Release Cycle
  - 2週間に1回出す
  - 間に合わないものは諦めて次に出す
    - 駆け込み乗車はおやめください
  - QAにとってスケジューリングがしやすい
- New Features
  - Feature Bloat
    - Feature Deplications
      - 似たような機能。課題
- Platform Updates

### Challenges

- Technical Debt
  - 技術的負債
    - メンバ全員が返すの無理なので分担したり、
    - 新機能も実装するけど、返すのもやったり、
    - 負債を返した人を評価することも大事
  - メトリクスを見ていかに負債を出さないようにするかに注力している
- UX
- DX ( Developer Experience )
  - Good UX comes from Good DX
    - Faster Build Speed
    - Better Development Environment / TOols
    - Better Development / QA / Release Process
    - More Automation : Testing, Deploy,,

### Future

- Plans / TODOs
  - More process automation
  - Catching up with platform evolution
  - Feature re-organization
    - 機能を整理
  - Build/release engineering
  - Code refactoring
  - More test code coverege
  - etc

## LINE Creators Studioで写真を簡単＆きれいに切り抜いてもらいたい話

- スマートフォンからLINEのスタンプが簡単に作れる
- 撮った写真を加工してスタンプにできる
- スタンプの審査申請や販売ができる
- 構成
  - Pure Kotolin
  - MVVM
  - Dagger2, RxJava2, RxKotlin, RxLifecycle, Retrofit2, OkHttp3, Glide, Realm, Anko, Espresso, Mockito-Kotlin
- History
  - 2017/06/12 ver1.0
- 切り抜き関連リリース多すぎ
  - 2番目くらいに多い不満
- なぞって切り抜き
  - 切り抜きたいもののフチをなぞると切り抜ける
  - フチは微調整できる
  - 指の下は見えないので操作しにくい欠点がある
- 形で切り抜き
  - 簡単だが用意された形でしか切り抜けない
- 消しゴム機能
  - 不要な背景などを消しゴムで消せる
  - 細かい調整ができるがユーザの負担は増えた
  - 指の下が見えない課題は上に拡大鏡を表示することで解決した
- デコフレーム
  - イメージをフレームでデコレーションできる
  - 同じような見た目のスタンプが量産されてしまう
- 自動切り抜き
  - 機械学習
    - remove.bgなどのサービスもある
    - Object Detection
      - ML Kit for firebase
      - [YOLO](https://pjreddie.com/darknet/yolo/)
    - Image Segmentation
      - Object Detectionして、画像の各1pxが何を表しているか判断する
    - TensorFlow Lite
      - モバイル向けのTensorFlow
    - スタンプ作成時のユーザーニーズ
      - 機械学習による領域検出だけでは足りない
      - ユーザによって画像のどの部分を使いたいかは違う
    - 実際のリリース
      - イメージの周囲をざっくりなぞってもらい、自動で切り抜く
      - 消しゴムや修復消しゴムをかけてもらう、自動切り抜きを何度か繰り返してもらう
      - やや難しい操作
      - チュートリアルは表示してるけど、それでもわかりにくい
      - 試してもらうことで徐々に理解はしてもらえるくらいの難しさ
    - GrabCut Alogrithm
      - OpenCV
      - ユーザが選択した領域から矩形を生成
      - GMMで前景/背景の画素数分布を学習、予測モデルを生成
      - モデルを用いてピクセルをつなぎグラフを構築する
      - ピクセルを繋ぐエッジの重みを計算し、総和が最小になるように切断する
      - ユーザに補正の線を入力してもらい、次の計算に使っていく
  - 処理速度向上のための工夫
    - RenderScriptを使う
  - 画質の向上
    - 行列を使って移動・拡大縮小・回転
    - ユーザの操作を元画像に対して適用できる
  - 美しさの向上
    - エッジにぼかしをかける
    - GrubCut用にはかけない、表示用にはかける

## LINEとLINE Creators Studio iOSアプリのサーバーAPI呼び出しアーキテクチャをリファクタリングした話

2017新卒！

- Agenda
  - LINE Creators Studio のログイン
  - LINE Messanger

### LINE Creators Studio のログイン

- LINEログインでユーザ管理
  - LINE SDK使用
  - v1 -> v2のアップデート
    - clientでtokenを持てなくなった
    - リファクタした
      - Creators Studio側はrefreshを無くし、loginだけにした
  - Observable<T>
    - onNext
    - onCompleted
    - onError

### LINE Messanger

- 複雑
  - スタンプの種類が多い
  - 画像の種類が多い
  - パッケージとスタンプ


## 懇親会

ビール100リットル
1人リットル！！！！！





