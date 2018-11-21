# Fukuoka.rb #115

2018/11/21 Wed GMOペパボさん
![RUBY](https://pbs.twimg.com/media/DshNgqlVsAEydAx.jpg "RUBY")


ハッシュタグ [#fukuokarb](https://twitter.com/search?q=%23fukuokarb)

## ruby
- [公式](https://www.ruby-lang.org/ja/)
  - [ドキュメント](https://www.ruby-lang.org/ja/documentation/)
    - 各バージョンのリファレンスマニュアルがある
    - 例えば [2.3.0](https://docs.ruby-lang.org/ja/2.3.0/doc/index.html)

## rubyを入れる
macにはもともと入ってるけどrbenvが便利らしい
[MacにHomeBrew,rbenv,bundlerをインストールする
](https://qiita.com/shinkuFencer/items/3679cfd966f6a61ccd1b)

### コマンド
```bash
$ # rbenvを入れる
$ brew install rbenv ruby-build
$ rbenv --version
$ # バージョンをリスト表示
$ rbenv install -l
$ # 2.5.3が最新っぽくて、2.6.xのリリースが近いらしい。
$ rbenv install 2.5.3
$ # 切り替え可能なバージョンを確認する
$ rbenv versions
$ # 切り替え前
$ ruby -v
$ # 切り替える
$ rbenv global 2.1.0
$ # 切り替え後
$ ruby -v
```

### 結果
```bash
loft-air:~ loft$ brew install rbenv ruby-build
Updating Homebrew...
==> Installing dependencies for rbenv: autoconf, openssl, pkg-config and ruby-build
==> Installing rbenv dependency: autoconf
==> Downloading https://homebrew.bintray.com/bottles/autoconf-2.69.sierra.bottle.4.tar.gz
######################################################################## 100.0%
==> Pouring autoconf-2.69.sierra.bottle.4.tar.gz
==> Caveats
Emacs Lisp files have been installed to:
  /usr/local/share/emacs/site-lisp/autoconf
==> Summary
🍺  /usr/local/Cellar/autoconf/2.69: 70 files, 3.0MB
==> Installing rbenv dependency: openssl
==> Downloading https://homebrew.bintray.com/bottles/openssl-1.0.2p.sierra.bottle.tar.gz
######################################################################## 100.0%
==> Pouring openssl-1.0.2p.sierra.bottle.tar.gz
==> Caveats
A CA file has been bootstrapped using certificates from the SystemRoots
keychain. To add additional certificates (e.g. the certificates added in
the System keychain), place .pem files in
  /usr/local/etc/openssl/certs

and run
  /usr/local/opt/openssl/bin/c_rehash

openssl is keg-only, which means it was not symlinked into /usr/local,
because Apple has deprecated use of OpenSSL in favor of its own TLS and crypto libraries.

If you need to have openssl first in your PATH run:
  echo 'export PATH="/usr/local/opt/openssl/bin:$PATH"' >> ~/.bash_profile

For compilers to find openssl you may need to set:
  export LDFLAGS="-L/usr/local/opt/openssl/lib"
  export CPPFLAGS="-I/usr/local/opt/openssl/include"

==> Summary
🍺  /usr/local/Cellar/openssl/1.0.2p: 1,793 files, 12.3MB
==> Installing rbenv dependency: pkg-config
==> Downloading https://homebrew.bintray.com/bottles/pkg-config-0.29.2.sierra.bottle.tar.gz
######################################################################## 100.0%
==> Pouring pkg-config-0.29.2.sierra.bottle.tar.gz
🍺  /usr/local/Cellar/pkg-config/0.29.2: 11 files, 627.1KB
==> Installing rbenv dependency: ruby-build
==> Downloading https://github.com/rbenv/ruby-build/archive/v20181106.tar.gz
==> Downloading from https://codeload.github.com/rbenv/ruby-build/tar.gz/v20181106
######################################################################## 100.0%
==> ./install.sh
🍺  /usr/local/Cellar/ruby-build/20181106: 420 files, 213.4KB, built in 14 seconds
==> Installing rbenv
==> Downloading https://homebrew.bintray.com/bottles/rbenv-1.1.1.sierra.bottle.1.tar.gz
######################################################################## 100.0%
==> Pouring rbenv-1.1.1.sierra.bottle.1.tar.gz
🍺  /usr/local/Cellar/rbenv/1.1.1: 36 files, 63.0KB
==> Caveats
==> autoconf
Emacs Lisp files have been installed to:
  /usr/local/share/emacs/site-lisp/autoconf
==> openssl
A CA file has been bootstrapped using certificates from the SystemRoots
keychain. To add additional certificates (e.g. the certificates added in
the System keychain), place .pem files in
  /usr/local/etc/openssl/certs

and run
  /usr/local/opt/openssl/bin/c_rehash

openssl is keg-only, which means it was not symlinked into /usr/local,
because Apple has deprecated use of OpenSSL in favor of its own TLS and crypto libraries.

If you need to have openssl first in your PATH run:
  echo 'export PATH="/usr/local/opt/openssl/bin:$PATH"' >> ~/.bash_profile

For compilers to find openssl you may need to set:
  export LDFLAGS="-L/usr/local/opt/openssl/lib"
  export CPPFLAGS="-I/usr/local/opt/openssl/include"

For pkg-config to find openssl you may need to set:
  export PKG_CONFIG_PATH="/usr/local/opt/openssl/lib/pkgconfig"

loft-air:~ loft$
loft-air:~ loft$
loft-air:~ loft$ rbenv --version
rbenv 1.1.1
loft-air:~ loft$
```
```bash
loft-air:~ loft$ rbenv install -l
Available versions:
  1.8.5-p52
  1.8.5-p113
  1.8.5-p114
  1.8.5-p115
  1.8.5-p231
  1.8.6
  1.8.6-p36
  1.8.6-p110
  1.8.6-p111
  1.8.6-p114
  1.8.6-p230
  1.8.6-p286
  1.8.6-p287
  1.8.6-p368
  1.8.6-p369
  1.8.6-p383
  1.8.6-p388
  1.8.6-p398
  1.8.6-p399
  1.8.6-p420
  1.8.7-preview1
  1.8.7-preview2
  1.8.7-preview3
  1.8.7-preview4
  1.8.7
  1.8.7-p17
  1.8.7-p22
  1.8.7-p71
  1.8.7-p72
  1.8.7-p160
  1.8.7-p173
  1.8.7-p174
  1.8.7-p248
  1.8.7-p249
  1.8.7-p299
  1.8.7-p301
  1.8.7-p302
  1.8.7-p330
  1.8.7-p334
  1.8.7-p352
  1.8.7-p357
  1.8.7-p358
  1.8.7-p370
  1.8.7-p371
  1.8.7-p373
  1.8.7-p374
  1.8.7-p375
  1.9.0-0
  1.9.0-1
  1.9.0-2
  1.9.0-3
  1.9.0-4
  1.9.0-5
  1.9.1-preview1
  1.9.1-preview2
  1.9.1-rc1
  1.9.1-rc2
  1.9.1-p0
  1.9.1-p129
  1.9.1-p243
  1.9.1-p376
  1.9.1-p378
  1.9.1-p429
  1.9.1-p430
  1.9.1-p431
  1.9.2-preview1
  1.9.2-preview3
  1.9.2-rc1
  1.9.2-rc2
  1.9.2-p0
  1.9.2-p136
  1.9.2-p180
  1.9.2-p290
  1.9.2-p318
  1.9.2-p320
  1.9.2-p326
  1.9.2-p330
  1.9.3-dev
  1.9.3-preview1
  1.9.3-rc1
  1.9.3-p0
  1.9.3-p105
  1.9.3-p125
  1.9.3-p194
  1.9.3-p286
  1.9.3-p327
  1.9.3-p362
  1.9.3-p374
  1.9.3-p385
  1.9.3-p392
  1.9.3-p426
  1.9.3-p429
  1.9.3-p448
  1.9.3-p484
  1.9.3-p545
  1.9.3-p547
  1.9.3-p550
  1.9.3-p551
  2.0.0-dev
  2.0.0-preview1
  2.0.0-preview2
  2.0.0-rc1
  2.0.0-rc2
  2.0.0-p0
  2.0.0-p195
  2.0.0-p247
  2.0.0-p353
  2.0.0-p451
  2.0.0-p481
  2.0.0-p576
  2.0.0-p594
  2.0.0-p598
  2.0.0-p643
  2.0.0-p645
  2.0.0-p647
  2.0.0-p648
  2.1.0-dev
  2.1.0-preview1
  2.1.0-preview2
  2.1.0-rc1
  2.1.0
  2.1.1
  2.1.2
  2.1.3
  2.1.4
  2.1.5
  2.1.6
  2.1.7
  2.1.8
  2.1.9
  2.1.10
  2.2.0-dev
  2.2.0-preview1
  2.2.0-preview2
  2.2.0-rc1
  2.2.0
  2.2.1
  2.2.2
  2.2.3
  2.2.4
  2.2.5
  2.2.6
  2.2.7
  2.2.8
  2.2.9
  2.2.10
  2.3.0-dev
  2.3.0-preview1
  2.3.0-preview2
  2.3.0
  2.3.1
  2.3.2
  2.3.3
  2.3.4
  2.3.5
  2.3.6
  2.3.7
  2.3.8
  2.4.0-dev
  2.4.0-preview1
  2.4.0-preview2
  2.4.0-preview3
  2.4.0-rc1
  2.4.0
  2.4.1
  2.4.2
  2.4.3
  2.4.4
  2.4.5
  2.5.0-dev
  2.5.0-preview1
  2.5.0-rc1
  2.5.0
  2.5.1
  2.5.2
  2.5.3
  2.6.0-dev
  2.6.0-preview1
  2.6.0-preview2
  2.6.0-preview3
  jruby-1.5.6
  jruby-1.6.3
  jruby-1.6.4
  jruby-1.6.5
  jruby-1.6.5.1
  jruby-1.6.6
  jruby-1.6.7
  jruby-1.6.7.2
  jruby-1.6.8
  jruby-1.7.0-preview1
  jruby-1.7.0-preview2
  jruby-1.7.0-rc1
  jruby-1.7.0-rc2
  jruby-1.7.0
  jruby-1.7.1
  jruby-1.7.2
  jruby-1.7.3
  jruby-1.7.4
  jruby-1.7.5
  jruby-1.7.6
  jruby-1.7.7
  jruby-1.7.8
  jruby-1.7.9
  jruby-1.7.10
  jruby-1.7.11
  jruby-1.7.12
  jruby-1.7.13
  jruby-1.7.14
  jruby-1.7.15
  jruby-1.7.16
  jruby-1.7.16.1
  jruby-1.7.16.2
  jruby-1.7.17
  jruby-1.7.18
  jruby-1.7.19
  jruby-1.7.20
  jruby-1.7.20.1
  jruby-1.7.21
  jruby-1.7.22
  jruby-1.7.23
  jruby-1.7.24
  jruby-1.7.25
  jruby-1.7.26
  jruby-1.7.27
  jruby-9.0.0.0.pre1
  jruby-9.0.0.0.pre2
  jruby-9.0.0.0.rc1
  jruby-9.0.0.0.rc2
  jruby-9.0.0.0
  jruby-9.0.1.0
  jruby-9.0.3.0
  jruby-9.0.4.0
  jruby-9.0.5.0
  jruby-9.1.0.0-dev
  jruby-9.1.0.0
  jruby-9.1.1.0
  jruby-9.1.2.0
  jruby-9.1.3.0
  jruby-9.1.4.0
  jruby-9.1.5.0
  jruby-9.1.6.0
  jruby-9.1.7.0
  jruby-9.1.8.0
  jruby-9.1.9.0
  jruby-9.1.10.0
  jruby-9.1.11.0
  jruby-9.1.12.0
  jruby-9.1.13.0
  jruby-9.1.14.0
  jruby-9.1.15.0
  jruby-9.1.16.0
  jruby-9.1.17.0
  jruby-9.2.0.0-dev
  jruby-9.2.0.0
  jruby-9.2.1.0-dev
  maglev-1.0.0
  maglev-1.1.0-dev
  maglev-2.0.0-dev
  mruby-dev
  mruby-1.0.0
  mruby-1.1.0
  mruby-1.2.0
  mruby-1.3.0
  mruby-1.4.0
  mruby-1.4.1
  rbx-2.2.2
  rbx-2.2.3
  rbx-2.2.4
  rbx-2.2.5
  rbx-2.2.6
  rbx-2.2.7
  rbx-2.2.8
  rbx-2.2.9
  rbx-2.2.10
  rbx-2.3.0
  rbx-2.4.0
  rbx-2.4.1
  rbx-2.5.0
  rbx-2.5.1
  rbx-2.5.2
  rbx-2.5.3
  rbx-2.5.4
  rbx-2.5.5
  rbx-2.5.6
  rbx-2.5.7
  rbx-2.5.8
  rbx-2.6
  rbx-2.7
  rbx-2.8
  rbx-2.9
  rbx-2.10
  rbx-2.11
  rbx-2.71828182
  rbx-3.0
  rbx-3.1
  rbx-3.2
  rbx-3.3
  rbx-3.4
  rbx-3.5
  rbx-3.6
  rbx-3.7
  rbx-3.8
  rbx-3.9
  rbx-3.10
  rbx-3.11
  rbx-3.12
  rbx-3.13
  rbx-3.14
  rbx-3.15
  rbx-3.16
  rbx-3.17
  rbx-3.18
  rbx-3.19
  rbx-3.20
  rbx-3.21
  rbx-3.22
  rbx-3.23
  rbx-3.24
  rbx-3.25
  rbx-3.26
  rbx-3.27
  rbx-3.28
  rbx-3.29
  rbx-3.30
  rbx-3.31
  rbx-3.32
  rbx-3.33
  rbx-3.34
  rbx-3.35
  rbx-3.36
  rbx-3.37
  rbx-3.38
  rbx-3.39
  rbx-3.40
  rbx-3.41
  rbx-3.42
  rbx-3.43
  rbx-3.44
  rbx-3.45
  rbx-3.46
  rbx-3.47
  rbx-3.48
  rbx-3.49
  rbx-3.50
  rbx-3.51
  rbx-3.52
  rbx-3.53
  rbx-3.54
  rbx-3.55
  rbx-3.56
  rbx-3.57
  rbx-3.58
  rbx-3.59
  rbx-3.60
  rbx-3.61
  rbx-3.62
  rbx-3.63
  rbx-3.64
  rbx-3.65
  rbx-3.66
  rbx-3.67
  rbx-3.68
  rbx-3.69
  rbx-3.70
  rbx-3.71
  rbx-3.72
  rbx-3.73
  rbx-3.74
  rbx-3.75
  rbx-3.76
  rbx-3.77
  rbx-3.78
  rbx-3.79
  rbx-3.80
  rbx-3.81
  rbx-3.82
  rbx-3.83
  rbx-3.84
  rbx-3.85
  rbx-3.86
  rbx-3.87
  rbx-3.88
  rbx-3.89
  rbx-3.90
  rbx-3.91
  rbx-3.92
  rbx-3.93
  rbx-3.94
  rbx-3.95
  rbx-3.96
  rbx-3.97
  rbx-3.98
  rbx-3.99
  rbx-3.100
  rbx-3.101
  rbx-3.102
  rbx-3.103
  rbx-3.104
  rbx-3.105
  rbx-3.106
  rbx-3.107
  ree-1.8.7-2011.03
  ree-1.8.7-2011.12
  ree-1.8.7-2012.01
  ree-1.8.7-2012.02
  topaz-dev
  truffleruby-1.0.0-rc2
  truffleruby-1.0.0-rc3
  truffleruby-1.0.0-rc5
  truffleruby-1.0.0-rc6
  truffleruby-1.0.0-rc7
  truffleruby-1.0.0-rc8
  truffleruby-1.0.0-rc9
loft-air:~ loft$
```

```
loft-air:~ loft$ rbenv install 2.5.3
ruby-build: use openssl from homebrew
Downloading ruby-2.5.3.tar.bz2...
-> https://cache.ruby-lang.org/pub/ruby/2.5/ruby-2.5.3.tar.bz2
Installing ruby-2.5.3...
Installed ruby-2.5.3 to /Users/loft/.rbenv/versions/2.5.3

loft-air:~ loft$
```

なんか、切り替わってないけど、とりあえず2.3で
```bash
loft-air:~ loft$ rbenv versions
  system
* 2.5.3 (set by /Users/loft/.rbenv/version)
loft-air:~ loft$ ruby -v
ruby 2.3.7p456 (2018-03-28 revision 63024) [universal.x86_64-dvarwin16]
loft-air:~ loft$ rbenv global 2.5.3
loft-air:~ loft$ ruby -v
ruby 2.3.7p456 (2018-03-28 revision 63024) [universal.x86_64-darwin16]
loft-air:~ loft$ rbenv versions
  system
* 2.5.3 (set by /Users/loft/.rbenv/version)
loft-air:~ loft$
```

```bash
 rbenv global system
loft-air:~ loft$ rbenv versions
* system (set by /Users/loft/.rbenv/version)
  2.5.3
loft-air:~ loft$ ruby -v
ruby 2.3.7p456 (2018-03-28 revision 63024) [universal.x86_64-darwin16]
loft-air:~ loft$
```

## hollo world
```
loft-air:1121 loft$ cat hello.rb
puts "Hello, world!"
loft-air:1121 loft$ ruby hello.rb
Hello, world!
loft-air:1121 loft$
```

## VS CodeのExtensionなど
https://qiita.com/kikunantoka/items/ebae7f71e0952a26a5dc

Extensionの`Ruby`を入れた。
以下が説明の見出し。Debuggerや補完機能に期待。
- Install
- Language Server
- Debugger
- Linters
- Formatting
- Autocomplete
- Intellisense (Go to/Peek Definition/Symbols)
- TODO
- Contributing
- License

## オススメの本など聞いてみた
なんと著者自ら本を紹介いただくなど
- [ゼロからわかるRuby超入門](http://pupupopo88.hatenablog.com/entry/2018/11/20/205127)
- [現場で使える Ruby on Rails 5速習実践ガイド](https://www.amazon.co.jp/dp/4839962227/)
- [改訂2版 Ruby逆引きハンドブック](https://www.amazon.co.jp/dp/B07GP1JYZH/ref=cm_sw_r_cp_ep_dp_c5t9Bb07CYZQE)

