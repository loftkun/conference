# 株式会社ベガコーポレーション イベントスペース

2019/05/14 Fri1

株式会社ベガコーポレーション さんにて

ハッシュタグ [#chibi_developer](https://twitter.com/search?q=%23chibi_developer)


## OSSのあれこれ話すイベントやりたいと思った

チャンカツさん

- 私がやってるOSS見てって
- OSS活動あるある
  - 英語
  - CIこける

## インフラ

ろーかるゆーざーさん

- 無償版のインフラ製品が出ている
  - 期限がないのがウリのものも
  - 仮想基盤
- EMC Unity VSA Community Edition
  - ストレージ
- DataDomain VirtualEdition Evaluation
- Isilon SD Edge Community Edition
- Veeam製品の無償版
  - 営業から鼻息の荒い電話がかかってくる

## gatsby + netlifyでサイトを作った話	

todaさん

- ポートフォリオを作ろうと思った
- 継続してアウトプットする場を作る
- gatsby
  - GatsbyのStarterから参考にするサンプルサイトを探す
  - 良いデザインのが多い
- netlify
  - GitHubと連携して画面ぽちぽちするだけ

## 福岡でガチエンジニアがブートキャンプをはじめる話

うづらさん

[ガチエンジニアがブートキャンプをやってみる話 / bootcamp-by-engineer-for-engineer - Speaker Deck](https://speakerdeck.com/udzura/bootcamp-by-engineer-for-engineer)

- 最近はrubykaigi、CNDFあったよ
- DAIMYO Engineer College
  - Ruby 超入門
- GitHub
  - haconiwa とか
- コード(OSS)書きたい人
  - だけど講師をやるぞ
- エンジニア 成長 アウトプット で検索してみると・・・
  - 講師陣がアウトプットしているところは意外とないのではないか
  - 本当にうづらはアウトプットしているのか？
    - 2016 は結構草
    - 最近半減、rubykaigiの準備とか

## postalk

- [postalk | オンラインの議論を加速させるカード型チャットツール](https://postalk.io/)
  - カード型チャットサービス
- エンジニアミートアップやります
  - [FGNエンジニアMeetup vol.1 - connpass](https://fgn.connpass.com/event/129569/)

## umeebe

海の住所

- ツリバカメラ
  - 撮った写真に位置情報をつけて共有できる
- 位置はエリアで管理している
  - Reverse Geocoding
    - 緯度経度から住所を割り出す
- Yahoo リバースジオコーディングAPI
- 海の上で釣ると位置情報は海上、住所がない
  - 市には代表点があり、最も近い代表点を採用している
  - 福岡市西区が糸島市になってしまう
  - 太平洋が東京になったり、ロシアから向こうが全部北海道になったりする
- エリア推定システム
  - 430万ポイントの代表点
  - 強い探索から弱い探索へ段階的に判定する
    - 2km, 4km, 10km
  - 沿岸部のポイントを増やす

## GANばった話

- マントをかぶると透明になるやつをやりたい
- 物体検出 + GAN = 透明マント
- GAN
  - Generative Adversarial Network
  - 警察官と詐欺師を用意する強化学習
- 人を検出してその部分を切り抜いて消している

## AbemaTVのコメントビューアを作る話

私のLT

[AbemaTVのコメントビューアを作る話 - Speaker Deck](https://speakerdeck.com/loftkun/abematvfalsekomentobiyuawozuo-ruhua)

## セキュリティの話


## イラスト布教

- Bamboo
  - 6000円くらい
- Intuos 2-3万
  - 高いけどこっちおすすめ

- グラデ塗り
  - レイヤ数が多いのPC性能が必要

- 作成工程の録画メモ

## けんてぃが考えるWebサイトの品質


- 建物の価値観に似ている
  - 基礎価値
  - 付加価値

## 思い立って一週間でスライド共有サービスを作った話

- showtimeのご紹介
  - スライド操作をスマホでできる

- Railsサーバとスマホの間でWebSocket通信している
  - それをPC(ブラウザ)で受信している
- スマホとPC(ブラウザ)でP2P通信させたい
  - WebRTCを使うことになりそう

## インフラエンジニアがBE/FEエンジニアにジョブチェンした話

- 理想を言えばきりがない
  - NoOpts
  - バランスが大事

## 英単語を覚えるためにWEBサービスを作った

[https://flash-cards-marvelous.firebaseapp.com](https://flash-cards-marvelous.firebaseapp.com/)

- Flash Cards
  - 単語帳
  - Firebase Authentication
  - Nuxt.js
    - SSRでなくSPAモード使ってる
  - vue-carousel
    - めくる時のアニメーション
  - 
  - Vue.Draggable
    - カードの並び替え
      - D&Dで列を入れ替えるやつ(jiraのアイテムならべかえるみたいなやつ)
- Demo

## 告知タイム

- 水耕栽培
  - ラズパイで液肥とか酸素濃度とかモニタリング
    - DataDogに投げたい
- 九州沖縄ネットワークオペレーターズグループ
