# ヤフー福岡 Tech Meetup #4

2019/06/21 Fri

エルガーラ 中ホール1にて

ハッシュタグ [#yjfukuoka](https://twitter.com/search?q=%23yjfukuoka)

## ヤフーデータの外部活用事例

- 位置情報の利用
  - 東京都 熱中症予測事業
    - オープンなデータ
      - 暑さ指数
    - 人混みに付随して熱中症になる状況が変わる
      - どうやってとる?
    - 場所をベースに出す情報
      - Yahooの防災速報の情報とか
  - 熊本地震前後の混雑から隠れ避難場所の推定
    - 公式避難所じゃないけど人が多いところ
      - 隠れ避難所ではないか
- 同じやり方で
  - イベント検出
    - 何か開催されてるのでは、とか？
  - 災害の頑強度
    - 混雑しやすいところ
- DATA FOREST

## 不均衡データ分析時のノウハウと注意点

- ゲーム業界からヤフーに入社
- ヤフーカードのデータ分析・機械学習
  - PayPayに紐づけられるのはヤフーカードだけ、絶対お得です

- 不均衡データ
  - 正解データ・不正解データの割合が大きく偏ったデータのこと
- 与信審査
  - 与信スコア
    - 貸し倒れリスクを表す
    - 線形回帰で出すことが多い
  - 正常会員に対する貸し倒れ率は0.5%
    - 10万人中500人くらい
- カード利用
  - オーソリゼーション(仮売上)
    - オーソリと略して呼んでる
    - オーソリの内、不正は0.2%程度
- 不均衡データの扱い方
  - 与信審査の特徴
    - 正常会員の特徴はそんなに変わらない
    - 会員数が多く、1万件以上の貸し倒れデータが存在する
    - アンダーサンプリングでOK
  - カード利用(オーソリ)
    - 正常利用の使い方にはある程度の特徴がある
    - 不正利用はトレンドの変化が激しく、過学習の可能性が高い
    - Isolation forest
      - 正常利用だけを学習させて正解かどうかを見る
  - [pandas-profiling/pandas-profiling: Create HTML profiling reports from pandas DataFrame objects](https://github.com/pandas-profiling/pandas-profiling)
  - モデルの評価
    - ROC曲線


## 画像分類データセット作成時のノウハウと注意点 〜ラーメン二郎データセットの事例を交えて〜

[画像分類データセット作成時のノウハウと注意点 〜ラーメン二郎データセットの事例を交えて〜 #yjfukuoka](https://www.slideshare.net/techblogyahoo/yjfukuoka)

- 偽物出品検知
- 出品時のタイトル推薦
  - メルカリが先にやってるやつ

- ディープラーニングによる画像分類の事例
  - ラーメン二郎知ってますか？
    - 結構手上がった
- 学習の流れ
  - モデルを学習する
    - 1万枚学習を1epochとして30epoch学習した
    - 30epochやってどこの時点が一番いいかはやってみないと
      - 最後が一番いいとは限らない
    - 学習用、テスト用の2分割ではダメ
      - 偶然テストデータで性能がでるパラメータを選んでいる可能性がある
      - 評価用として、データセットの一部を学習に使わず残しておく必要がある
  - データセット作成
    - ラーメン二郎はTwitter/Instagramで集めた
    - 画像収集時にメタデータも集める
      - コメントやラベル
      - EXIF
  - データ前処理
    - クリーニング
      - 店名など、つぶやきのデータが間違っていることもある
      - 重複した画像も多い
        - バイナリ一致でなく、知覚ハッシュ関数で似た画像を検出できる
        - ![](https://pbs.twimg.com/media/D9lHvJ7VUAAEkNE.jpg:large)
      - オープンデータも意外とクリーニングされていない