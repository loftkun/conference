
# HAKATA Test Night #1

https://testnight.connpass.com/event/102776/

LINE Fukuokaさんにて

ハッシュタグ [#hakata_test_night](https://twitter.com/search?q=%23hakata_test_night)

![]()

## 15分枠(1)：tarappo：「Xcode10でのテスト周りの進化をふりかえる」

Execute parallel in Simulator

WWDC 2018 要チェック！

Androidテスト全書 4, 6章

iOSテスト全書キックオフ

## 15分枠(2)：Hiroaki OZONO：「Feature Detection for UI Testing」

テスト自動化チーム

E2E UIテスト

- ブラウザのテストSelenium
- モバイルアプリAppium

kubernetes常にブラウザをたくさん立てたりしている

### UIテストへの画像認識技術への応用

LINEのトーク占い

- Template画像がSource画像に表示されているか確認
- 表示されていればその座標をクリック
- OpenCVを使う

Template Matching

- 1pxずつずらして一致する箇所を見つける
- scaleや角度が変わると使えない
- displayサイズ毎にtemplate画像が必要

Feature Detection(特徴量検出)

- 拡大縮小・回転に強い
- A-Kaze特徴量
  - OpenCV3に入っている、各言語から使える

Appiumにも同じような機能が組み込まれている

## 15分枠(3)：ktanaka117：「トークンリフレッシュ処理を含むAPIClientのテスト」

ダンボー田中さん

ピクシブにてBOOTHというアプリを開発している

作家を応援できる

### 本題

新しいAccess Tokenが速攻で無効になる

Android OkHttpライブラリを参考にiOSで実装

### 本題

どうテストするか

テストケースはPlantUMLでUML(シーケンス)を書いてリポジトリ管理している

テストコードの近くにUML画像のリンクを貼っている

テストコードの見た目をテストケースに近づけてリーダブルに


## 5分枠(1) ：fromkk：「Firebase Test Lab for iOSを触ってみた」

Firebase Test Lab

テスト結果をスクショだけでなく、動画でも残せる

gccloudコマンドで使用できる

## 5分枠(2) ：fromkk：「Closure Injectionでテストが書けた:tada:」

DI

- Constructor Injection
- Setter Injection
- Property Injection

Clousure Injectionと勝手に命名

差し替えられるようにした

## 5分枠(3) ：nesskazu：「Bitrise STEP 紹介」

CI/CD

Slackにでデプロイ結果のQRコードを通知、メンバはそれをインストール







