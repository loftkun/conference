# Go 1.13 Release Party in Umeda

2019/08/23 Fri

ナレッジサロン グランフロント7F さんにて

ハッシュタグ [#go113party](https://twitter.com/search?q=%23go113party)

[sli.do](https://app.sli.do/event/zlv6h9vz/live/questions)

## What's new Go1.13? by tenntenn

- [Go 1.13 Release Notes - The Go Programming Language](https://tip.golang.org/doc/go1.13)
  - 数値リテラルの変更
  - GO111MODULEはdefaultでauto
  - GOPROXYのデフォルトがproxy.golang.orgに
  - go env -w で環境変数が変更できるように
  - パッケージ
    - errors
      - %w
    - testing
      - Init関数が入った

## GopherCon 2019 Report by knsh14

- メルカリはシルバースポンサー！
- [gomods/athens: A Go module datastore and proxy](https://github.com/gomods/athens)
  - A proxy server for Go modules
  - 他にもプロキシの実装あるけどこれが人1番多い
  - proxy.golang.orgと同じAPIを実装している
    - 用途
    - audit log取りたいとか
    - S3とかにキャッシュする用途で使えるぞ
  - コンテナイメージ gomods/athensがあるのですぐに試せるぞ

## What's new sync.Pool in Go1.13 by huydx

- [sync.Pool](https://golang.org/pkg/sync/#Pool)
  - 何？
    - interface見ると Put()とGet() があるくらいなもんだぞ
  - 歴史の話
    - 1.13
      - lock free !
      - Make GC less spiky

## Talk from Fukuoka.go

- あらためてGenericsを知る
  - GenericsはGo2の機能でコードの柔軟性や表現力を与える
- Genericsとは？
  - コードの具体的な要素である型などを除外してアルゴリズムとデータ構造を汎用的形式で表現
- サンプルコードで見てみよう
  - sliceを逆順にするメソッド
    - ReversInt(i []int)
    - ReversString(s []String)
  - 型が違うだけでコード(アルゴリズム)がほぼ一緒
  - 型に依存する処理がない
  - Reverse(type T)( s []T)
    - 呼び出し側で型を明示する
      - Reverse(int)([]int{1,2,3})
- 型に依存する処理があると？
  - エラーになる
  - contractというものがある
  - Tの制限を記述できる

## testing.B.ReportMetric by ymotongpoo

- Google Cloudの中の人！
- [O'Reilly Japan - Go言語による並行処理](https://www.oreilly.co.jp/books/9784873118468/)の訳者！

- Measurement in Go
  - Goは計測に関するパッケージやツールが豊富
  - testing.B
    - ReportMetric
      - 自分でメトリックを定義して結果表示できる
  - benchstat
    - compare diffs of 2 benchmark result
      - どれくらい良くなったかとか

## net/http by shibu_jp

- net/httpが再設計されつつある
  - client部分の設計が陳腐化してきている
  - 問題点
    - パッケージが巨大すぎ
    - client側はミスを誘発しやすいAPI
      - プログラマ側が気をつけることが多い
        - ステータスコードチェックとか
        - Close()が必要だったりとか
    - client serverでコードを共有している
    - お互い参照しまくってたりする
    - など
- 新しい設計案
  - コンテキストをもっと便利に
  - よく使われるケースは短く
  - ジェネリクスも活用
  - サーバーみたいにハンドラを付与？
  - など、検討中
- まだリリースはされないけど、我々は何をすべきか？
  - とりあえずContextを使うように徹底する
    - 方法1 1.13のNewRequestWithContextを使う
    - 方法2 http.Getなどをgolang.org/x/net/context/ctxhttpのGetなどに置き換える

## After Party


