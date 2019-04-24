# 【福岡】CircleCI ユーザーコミュニティミートアップ #1

2019/04/18 Thu

[【福岡】CircleCI ユーザーコミュニティミートアップ #1](https://circleci.connpass.com/event/123859/)

株式会社 Fusic さんにて

ハッシュタグ [#circlecijp](https://twitter.com/search?q=%23circlecijp)

![](https://pbs.twimg.com/media/D4bU_M7UEAI1jbC.jpg:large)

## CircleCIユーザーコミュニティについて

## セッション1: OSSで活用するCircle Ci

株式会社 Fusic [せいけしろー(@seike460)さん | Twitter](https://twitter.com/seike460)

[スライド](https://slide.seike460.com/slides/circlecijp_fukuoka_1#/)

- CircleCI完全に理解した、のグラフ

- CirrleCI
  - 実質無料
    - 超人気OSSに成長した場合は別
- Badge設定
    - Build Status
      - READMEに表示できるぞ
      - README用のMarkdonwを発行できる
    - Release
      - こういうやつ
        - ![](https://img.shields.io/github/release/faultline/faultline.svg)
        - ![](https://img.shields.io/github/release/fictionbase/fictionbase.svg)
    - Coverage
      - `.codecov.yml`を配置する
      - `.circleci/config.yml`にcodecovへのデータ送信コマンドを追加する

## セッション2: CircleCI 検定 9 級から 8 級になりました 〜 CircleCI 初心者の小咄 〜

[Yohei Kawahara（かっぱ）(@inokara)さん | Twitter](htts://twitter.com/inokara)

[2019-04-18 CircleCI Meetup Fukuoka #1 - Speaker Deck](https://speakerdeck.com/inokappa/2019-04-18-circleci-meetup-fukuoka-number-1)

- YAMAP
  - 電波が届かないところでも現在位置がわかる登山アプリ

- CircleCI検定とは
  - 架空の認定試験制度
  - ローカルPCでも実行できる
- ビルド環境にSSHでログインすることができる
  - デバッグとかできる
- workflow
  - job
- キャッシュを用いたビルドの高速化
  - save_cache
  - restore_cache :
    - keys :
      - 複数指定できる
      - キーがない場合はスキップされる(save_cacheも)
  - 今のところキャッシュを消す術はない


## セッション3: CircleCI APIでプチ効率化

株式会社 Fusic 櫻川さん

- API
  - ユーザー
  - プロジェクト
    - プロジェクトを新規フォロー
  - ビルド・ジョブ
    - ジョブの情報を取得
    - ジョブを実行
  - キー
  - Artifacts

## LT1: CICDを始める前に...ビルドデプロイについて再入門

[kato 4/18−19 福岡居ます。(@kuromitsu_ka)さん | Twitter](https://twitter.com/kuromitsu_ka)

[CICDを始める前に...ビルドデプロイについて再入門](https://www.slideshare.net/harukikato1/cicd-141118005)


## LT2: 並列化でテストを効率化する（仮

[夏目祐樹(ルシフ)(@sinofseven)さん | Twitter](https://twitter.com/sinofseven)

[CircleCI_のJobを_並列で実行してみる - Speaker Deck](https://speakerdeck.com/sinofseven_/circleci-falsejobwo-bing-lie-teshi-xing-sitemiru)

検定の最後の問題で解説されてしまった・・・・

この書き方あるんやな

``` shell
      commmand: |
        set -x
        (略)
        いろいろコマンド書ける
        (略)
```

## 今後のコミュニティ活動

ユーザーコミュニティリーダー募集中！

イベントスペース貸してくれる企業募集中！

