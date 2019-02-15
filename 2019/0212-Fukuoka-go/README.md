# Fukuoka.go#13+Okayama.go

2019/02/12 Tue

GMOペパボ株式会社さんにて

ハッシュタグ [#fukuokago](https://twitter.com/search?q=%23fukuokago)


![看板](https://pbs.twimg.com/media/DzMqogCUcAA_gfl.jpg)

![ドリンク](https://pbs.twimg.com/media/DzMqpKJVAAAd-rx.jpg)

![PC](https://pbs.twimg.com/media/DzMqpwvVAAAOc_9.jpg)


## dragon-importsで始める爆速goimports生活 by @monochromegane

goimports

- 外部パッケージの探索が遅い(1secかかる)

dragon-importsを作った

- 外部パッケージを見る1secがなくなった

## Goluaに触れてみる by take-cheeze

- Golangによるlua実装

## Goでコマンドラインツール作ってプロダクション投入した話 (仮) by @qt-luigi Okayama.go

サーバはWindows7 32bit デスクトップマシン！

goは32bitでも動く！

## Go を daemon化する方法 (仮) by @seike460

- サーバの情報を集めるエージェントを作りたい
  - デーモン化したい

- Goで頑張る
  - TTYと切り離してバックグラウンド実行
  - PIDを(ファイル出力)保持してシグナルを受けれるようにする
    - シグナルのハンドリング
      - signal.Notify
  - 既存のライブライもある
- Goで頑張らない
  - supervisord
    - プロセス管理ツール

## Go Modulesを理解する by @linyows

- `export GO111MODULE=on`
  - 1.2ではdefault onになるはず
- [direnv](https://www.softantenna.com/wp/review/direnv/)


## 休憩

## nanafshiを使って簡単に作るFUSEの動的ファイル by @tokibi

- FUSE
  - ユーザ空間上でファイルシステムを作れる
  - /dev/fuse
- ライブラリある
  - `hanwen/go-fuse`
    - sampleが豊富で理解しやすい
  - `nanafushi`

## rcon を go で実装してみた by @kunit

rcon
  - cgroupsを使ってプロセスのリソース管理
  - 例
     - バッチプロセスに対してCPU, メモリ使用量を制限

## [WIP] Git-Server with Go + gRPC + libgit2 by @vvatanabe_ja


## 不正なクエリを検知するsqdを作った (仮) by @komei5296



## Prometheusのexporterを作ってみた＋α (仮) by @transnano


