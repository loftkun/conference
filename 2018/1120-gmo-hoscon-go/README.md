# 【Go言語初心者向け】Go Webアプリを動かしてみようハンズオン@福岡

ハッシュタグ [#hoscon](https://twitter.com/search?q=%23hoscon)

## 事前準備
- go入れた
- ロリポップ！マネージドクラウド
  - アカウント作成、クレカ登録
  - SSH公開鍵登録

## 資料
[pepabo/todo-backend-golang-mc](https://github.com/pepabo/todo-backend-golang-mc)

## デプロイ
年内は無料で、削除しないと課金されるので注意

- バックエンド golang-hoscon-20181120.lolipop.io
- フロント + バックエンド todobackend.com/client/index.html?https://golang-hoscon-20181120.lolipop.io/todos

## 実装など
- Makefile
  - かっこいい、お手本になる。
  - sshはこういう感じでコマンドも実行できるらしいぞ
    - `ssh -p ${SSH_PORT} ${SSH_USER}@${SSH_HOST} 'mkdir -p /var/app/releases`

- 依存関係
  - go.mod
    - ここに書かれた階層に従って$GOPATH配下にパッケージが落とされてくるらしい
  - go.sum
    - これは自動で作られるので気にしなくて良い

- テンプレート
  - 値の埋め込みなどは以下のパッケージの機能を使っている
    - html/template

- ローカルの開発
  - docker入れた直後は失敗したけど、再トライしたらOKだった
  - http://localhost:8080/ でローカルで画面が見れた

- main.goで一行だけこうなっているのは？

``` go
	_ "github.com/go-sql-driver/mysql"
```

mysqlの公式にこのおまじないが書いてあるらしい
このパッケージの機能を使ったコーディングはないが、
初期化的なことをさせるために、importしているらしい

以下のように別名をつけて使えることを利用して、
mysqlについては使われないだろう別名的なもの(_)をつけているらしい

``` go
	chi_hogehoge "github.com/go-chi/chi"
```

## Goについて
- GOPATH
  - 設定されてないので設定しておいた方が良さげ

``` bash
loft-air:~ loft$ echo $GOPATH

loft-air:~ loft$
```

以下らへんが良さそう

``` bash
loft-air:~ loft$ ls -alh /Users/loft/go/pkg/mod/
total 0
drwxr-xr-x  4 loft  staff   136B 11 20 19:31 .
drwxr-xr-x  3 loft  staff   102B 11 20 19:31 ..
drwxr-xr-x  4 loft  staff   136B 11 20 19:31 cache
drwxr-xr-x  6 loft  staff   204B 11 20 19:31 github.com
loft-air:~ loft$
loft-air:~ loft$
```

上記はGOPATH=~/goなのでこれを設定しておくことしようと思う

## その他

- vimでメソッド探す機能使ってるぽいな(vim-go ほげほげ)
