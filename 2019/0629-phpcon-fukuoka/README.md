# PHPカンファレンス福岡2019

2019/06/29 Sat

福岡ファッションビルにて

ハッシュタグ [#phpconfuk](https://twitter.com/search?q=%23phpconfuk)

## 開会式

[TIMETABLE](https://phpcon.fukuoka.jp/2019/)

## PHP型検査・夢と理想と現実

[うさみけんた(@tadsan)さん | Twitter](https://twitter.com/tadsan)

- コーディングにはPHPStorm, PHPStanを活用しよう
  - PHPStormはハードル低い(お金以外は)
- 複合型
- 特殊型
- declare
- Phan
  - 静的解析ツール

## Monitoring PHP

[せいけしろー(@seike460)さん | Twitter](https://twitter.com/seike460)
[slide.seike460.com](https://slide.seike460.com/slides/phpconfuk2019#/)

プラチナのスポンサーのFusicさん！

- メトリクスとは
  - 取ろうと思えばなんでも取れる
  - では、PHPにおけるキーメトリクスはなんだろう
- Webなら
  - StatusCOde
  - レスポンス数
  - 応答速度
- PHPなら
  - Active/Idel Processes
  - :
- DBなら
  - クエリ発行数r
  - :
- モニタリングツール
  - push型/pull型がある
- Prometheus
  - exporter一覧
    - だいたいあるんで、作る必要ないぞ
  - 可視化はGrafanaが多い
    - Datadog
      - push型
  - APM : Application Performanc Management
    - デモ
      - MySQL

## 子育てとスキルアップを両立するエンジニアの生存戦略

プラチナのスポンサーのFusicさん！

- 3つの観点
  - xxxを増やす
    - 時間
      - 朝方に切り替える
      - xxxを活用する
        - 通勤時間
          - 電車やバスで勉強する
          - やりたいことをメモする(アプリとかで)
      - 会社としての施策
        - リモートワーク
  - xxxの質を高める
    - インプット
      - 社内Slackで情報収集している人が多かった
        - #techチャンネルがある
      - 社内の集合知を活用する
        - ナレッジベース(tamel)
          - 技術と人の紐付け
          - #helpチャンネルがある
      - 会社としての施策
        - 書籍購入制度
    - アウトプット
      - 機会を作ることが重要
      - 登壇する
        - 登壇駆動開発
      - Qiita
      - 会社としての施策
        - 開発合宿
  - xxxを大事にする
    - 家族
      - うまく連携する

## エンジニア向け社内イベントの進化の歴史

[goodoo(@goodoo)さん | Twitter](https://twitter.com/goodoo)

- あした会議
  - 1泊2日の合宿
- 第1回 APIを作る速さを競う個人戦
  - ゲームの仕様書を元にAPIを作る
    - 参加者にはサーバを渡し、DBのデータをimportするところから
    - 言語、フレームワークは自由
  - 反省
    - API作るところ以外に時間取られる人が多かった
      - 環境構築の時間を減らそう
- 第2回
  - DBデータはimport済み
  - 反省
    - レギュレーションが厳しすぎた
      - APIは動いているが点数がつかない人が多かった
        - 採点システムは難しい
- 第3回
  - チューニングに振り切った個人戦
    - ISUCON5をベースにシステム構築
      - 遅く設計されたWebシステムを用意
        - ベンチマーカーも用意済み
          - 負荷をかけて採点してくれる
    - DBチューニングの比率が高くなりすぎてハマった人が多かった
      - プログラミングに重きをおくべきだった
- 第4回
  - 過去の経験をちりばめたお題にした
    - inedexがイケてないとか
    - ループ内でSQL叩いているとか
  - 反省
    - 割と意図通りに取り組んでもらえた
- 目立たせる上での狙い
  - 絶対に連覇はさせないようにお題を用意する！
    - 新卒のコーディングの速さ VS ベテランの経験・チューニング力
- トランザクティブメモリー
  - 組織の誰が何を知っているかを把握すること

## Webサービスの成長を止めずにリファクタリングする技術

( 途中から聴講)

- デザインパターン
  - GOF
    - adaptorとか
- 実際にリファクタリングしましょう
  - テストを書きましょう
    - 責務が多くてテストが書けません
      - テストができる状態を目指す
        - 疎結合にする
        - テスト実行環境を作る
        - 振る舞いを明確にする
- 主なテストの種類
  - 何をテストしたいのか？
    - 機能要件ベース
      - シナリオテスト
    - コードベース
      - ユニットテスト
  - いきなり完全自動化しなくていい
- 責務が多すぎてユニットテストが書けないなら
  - **まずはシナリオテストにしよう！！**
    - シナリオテストが通るようにリファクタしていく
- シナリオテストに必要なこと
  - 本番相当のテストデータ
  - 本番相当のテスト環境(staging)
  - 明確な機能要件
- いきなりシナリオテストを自動化しない
  - selenium, phantomjsとか使うやつ
  - シナリオは変化しやすいから
  - Viewに近いところはビジネスの影響を受けやすい
  - 要件を絞る
  - フルテストみたいなシナリオを書かない
    - ログインだけ
    - 予約する機能だけ
      - Aパターン、Bパターンだけ
  - シナリオテストができたら
    - 機能を分解していく
      - **その時はユニットテストを最初から書け！！**
      - TDDじゃなくてもよいけどテストは書く
- Viewから遠いところからテストを書く
  - ドメイン層(プレゼンテーション層とデータ層の間)から着手する
    - ビジネスロジック
    - Entity
    - Repository
  - 何年も稼働しているサービスならビジネスロジックのコアは見えているはず
    - 変化のインパクトが大きいからこそリファクタリングとテストが活きる
- 新規開発とリファクタリングの共存
  - サービスレイヤがないなら導入する
  - 新規は最初からサービスレイヤ書いていく
    - 既存を少しずつサービスレイヤに移行
- 実際にリファクタリングした例
  - オミカレのフルリニューアル
    - テーブル設計に不備があった
      - 1つ1つ改善してきた
        - 別資料見てね
        - AuroraからPostgresに移行
          - 移行分はoldに、少しずつnewに移行
          - 新規分はnewに
      - APIはIN/OUTが明確
        - テストコードが書きやすい
    - 1つのモデルの責務が大きい
      - データアクセスとロジックが同じクラスに書かれている
      - Controllerに一部のロジックが漏れている
        - getParty()から取ってきた値を福岡用、とかに修正
      - /api/public/party
        - APIを呼び出すrepositoryパターンのPartySearchを作る
          - パラメタをSetして呼び出すだけ
        - PartySearchを使うPresenter
          - Presenterの中に検索条件が増えていく
            - Presenter(ビジネスロジック)とRepository(データアクセス)を繋ぐModel(データ加工)を用意
              - テストを書きやすい
                - PresenterはModelのモック(json)を扱うのでDBなくてもテストができる
    - FatController
      - 5000行超え
        - SEOのために必要なパンくず
          - if分が増える
            - Controllerにロジックが漏れている例
        - Presenterに責務を移していく
          - Presenterは先に作れる
            - 他の開発の邪魔をしない
    - Viewにif分を書いていませんか？
      - <?php if()><?php else><?php endif>
      - if分があるとはViewが状態を持っているということ
        - Viewに状態があるとテストしにくい
      - そもそもViewはテストしにくい
        - 見た目のテストは成否が難しい
        - ブラウザなどの依存関係
        - できるだけViewでテストしたくない
          - if文を書かない
      - Viewにif文を禁止しました

## 古き良き開発現場に新しい文化を作ろう！〜荒れた荒野を耕し、種を撒き、水を与え続ける話〜

[ナコ先輩(@nako0123)さん | Twitter](https://twitter.com/nako0123)

資料はあとで公開とのこと

早いのでメモ取り割愛、とても良い資料&発表

- ドキュメントビルド
  - [MkDocs](https://www.mkdocs.org/)
    - markdownをドキュメントにできる
    - GitLab CI/CDでGitLab Pagesに掲載


## ユニットテストの現場の問題を原則に立ち返って考える

[Kazuki Higashiguchi(@hgsgtk)さん | Twitter](https://twitter.com/hgsgtk)
[ユニットテストの現場の問題を原則に立ち返って考える / think deep unit test practical problem - Speaker Deck](https://speakerdeck.com/hgsgtk/think-deep-unit-test-practical-problem)

- ユニットテスト
  - このトークでは自動化テストを取り上げる
- 目的
  - このトークではコストの削減
- xUTP
  - 原則
- Obscure Test 曖昧なテスト
  - 何やってるかわからない
  - 適切なエラーレポートを出す
    - `Why does Go not have assertions`
    - 本当はこうであって欲しかったをレポートに込める
- 不安定なユニットテスト
  - 実行順序で結果が変わるやつとか
    - `keep tests independent` (xUTP)
  - `Minimal fixture`
  - `Shared fixture`
- 変更頻度が高いユニットテスト
  - 内部実装(protected/privateなメソッドとか)に依存するテスト
    - `Fragile Test` 壊れやすいテスト
    - `Overspecified Software`
      - 過剰に検査しているかも
      - テスト対象は可能な限りFront Door(正面玄関 public interface)を介するべき
        - privateメソッドをpublicにするかどうか
- mockが妨げるユニットテスト
  - xUTPによる語彙整理
    - MockはTest Doubleの中の1つだと定義される
  - コマンド(外の世界を変化させる)
  - クエリ(変化させない)
    - アローアンス
      - 何回呼んでも変化しない
