# #0 Fukuoka.Firebase@LTイベント

2019/02/21 Thu

株式会社Fusic さんにて

ハッシュタグ [#fukuokafirebase](https://twitter.com/search?q=%23fukuokafirebase)

![]()

## 自社サービスのチャット機能を自作からFirebaseに乗り換えた話

<br>
<br>

## AuthからはじめるFirebaseの第一歩

[スライド](https://twitter.com/massyuu85/status/1098538481494552577)

- Firebase Authentication
  - Firebaseが提供しているユーザ認証機能
  - SDK
    - Android, iOS, WEB(js)

- Vue.jsでログインするだけのものを作る
  - firebase().auth().signin

- UI Auth
  - `<div id="firebaseui-auth-container"></div>`だけで
    - Google, Twitter, Emailログインボタンが表示される

## JSでFirebaseのML Kitを使う

- 親富孝通りでGeek Studioというコワーキングスペースをやっている

- 無料SSL化が嬉しい
- ML Kit
  - Machine Learning Kit
    - iOS, Android
    - Native Scriptならいけるかも・・・
      - Native Script Firebase
  - Text Recoginition
    - デモ
      - カメラ映像の文字が認識できた
  - Face Recognition
    - デモ
      - カメラ映像の顔の笑顔かどうか判定できた

## Firebaseアプリ開発のテストについて考えてみる

- unitテスト
- E2Eテスト

- Console Suimulator
  - 手動でのテスト
- Local Emulator
  - Jest/Mochaなどでテストを書いていく感じ
  - カバレッジとかも出してくれる
  - CIで自動化
- デモ
  - github.com/firebase/quick start nodejs にある
- `firebase serve`
- firebase functions test
  - config値のモック
  - 




