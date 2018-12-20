# オープンソースカンファレンス 2018 Fukuoka

2018/12/08 Sat

https://www.ospn.jp/osc2018-fukuoka/

於 福岡ソフトリサーチパーク センタービル

ハッシュタグ [#osc18fk](https://twitter.com/search?q=%23osc18fk)

アンケートのくじでMariaDBぬいぐるみストラップをもらう(鐘鳴らして頂いたので良い景品！)
![MariaDB](https://pbs.twimg.com/media/Dt3VHEnUUAEk3V4.jpg "MariaDB")

## AI画像解析API 、4社のコードを比較してみる
画像解析にフォーカスしたお話

簡単にできるAPIサービス

- Azure Cognitive Services
- Google Cloud Vision API
- Amazon Rekognition Image, Video
- IBM Watson Recognition

利用料金の話
デモで使っているが無償枠を超えたことはない

別紙資料に環境構築手順があるぞ！

### デモ

4ベンダーの結果がjsonで返ってくる結果を並べる構成

Python

#### Azure

パラメタ

- Tags
  - 画像に関連する単語で画像にタグをつける

iPhoneを握ってる画像を渡すと

a hand holiding iphoneというtextが返る

#### Google

Annnotationが返ってくる

gadget, mobile phone,,,

type

- TEXT DETECTION
- FACE DETECTION

#### AWS

boto3というライブラリ使用

Azure, GoogleはREST呼び出しを自分で書く必要があるが、

AWSはboto3のAPI呼び出しで良い

Labelsが返ってくる

Electronics,Cell Phone,,,

顔が一致する画像を検索できる機能もあるらしい

#### IBM Watson

APIのバージョンは日付になってて日付で指定

scoreでソートされてないので自前でソートした

classが返ってくる

stereo system, audio system,,,(ちょっとずれてる・・・？)

### まとめ

精度はGoogle, AWS

画角、光源でかなり変わる

## オープンデータをAPIで使ってみよう！

オープンデータの定義

福岡県オープンデータ

### CKAN

Dockerイメージあり

### API
http://data.bodik.jp/

http://data.bodik.jp/api/3/action/package_search?q=organization:401307

### サンプルコード
```
brew install python3
pip3 install ckanapi
```

以下を追加すると詳細が表示できたぞ！
```
import pprint


pprint.pprint(pkg)
```

緯度や経度が表示できたぞ！

## オープンデータを使ったモバイルアプリ開発講座（入門編）

### Expo

React Nativeの開発を支援するツール

### SNACK

Webブラウザで開発できる

アカウントを作った

https://expo.io/@loftkun

スマホアプリ`Expo`をインストールした

SNACKのsnakタブのcreate snakから新規作成

QRコードを`Expo`アプリで読み込むとアプリが立ち上がる

WebUIでコードを変更するとほぼリアルタイムにアプリ側に反映されたぞ！！

https://expo.io/@loftkun/empty


https://snack.expo.io/@loftkun/evacuationspot

https://snack.expo.io/@tygoto/step1_map

アプリに地図が表示されたぞ！
![避難所アプリ](https://pbs.twimg.com/media/Dt3oShGU8AE9Fgu.jpg:large)

SNACKのログに避難所データが表示されたぞ！

避難所のピンをクリックすると詳細画面(DetailComponent)が表示されたぞ！

## オープンデータを使ったモバイルアプリ開発講座（応用編）

Reactの講義

いろんなサンプルを動かしてみる

- 顔認識
- 歩数計
- カメラ
  - Instagramのカメラはこれで作られてるので、同じくらいのものは作れる！

## オープンソースで始めるAR/VR開発

https://soil.connpass.com/event/107295/

### AR/VR デバイス紹介

### 体験から開発へ

- A-Frame
  - 今日のイチ押し！
- Mixed Reality ToolKit
  - HoloLens
- HoloKit
  - HMDも自作可能

#### A-Frame

Webブラウザ上で3Dを簡単に実現できる

WebVR

HTMLタグで記述

- a-xxxタグ
  - 図形
    - a-box
    - a-sphere
    - a-cylinder
    - a-plane
  - アニメーション
    - a-animation
      - 等速はeasingにlinearを設定する

https://aframe.io/

MacのChromeだと動かないかも

Safariは動いた

https://aframe.io/docs/0.8.0/introduction/

glitch上でHTML書いてすぐに動かせる
公開用URLもすぐ発行される

https://glitch.com/~aframe

もちろん自前でサーバを用意して置いてもいい

テクスチャマッピングもできる

- 球＋地図画像＝地球儀

背景にも画像を貼れる

thetaの画像を貼り付けると360度内覧できるコンテンツが作れる

360度ビデオもできる

3Dデータ

-　obj
-　glTF
-　COLLADA

#### AR

AR.js

ARTookKitベース

マーカー(正方形の枠)を撮影すると認識してCGをリアルタイムで表示する

js追加しただけで、カメラの許可が出て、背景がカメラ映像になった

HTMLタグ

- a-marker

![AR](https://pbs.twimg.com/media/Dt4SMuYVsAETj0m.jpg)

#### MR TookKit


## 閉会式

### LT

#### 東アジアの漢字

#### ラズパイ SORACOM LTE-M BUtton

Dashボタンのハック

SORACOM LTE-M BUtton

- シングルクリック
- ダブルクリック
- 長押し

Lambdaで何かするのに便利

- Tweetする
- Slackに投稿する

#### 南島原 アイデアソン、ハッカソン

オープンキャンプ

- ラズパイハンズオン
- カレーを作る

#### OSC アドベントカレンダー

松屋カレンダー も

#### ラズパイ

今日200台配ってた

企業から譲り受けた

2台余ったので懇親会で！

#### 自己紹介

ナミビア

OSSの活動をアフリカでしたい

日本 --> アフリカ OSSの橋

### 閉会の挨拶

#### SRP Open Innovation Lab

3月にオープン

交流の場所として無料で使える！！

10人くらいがちょうどいい

#### Engineer Friendly City

来週 イベント(Compass)

お疲れ様でした！