#ふくばねてす node-2

2019/07/11 Thu

Fukuoka Growth Next (大名小跡地)にて

ハッシュタグ [#ふくばねてす](https://twitter.com/search?q=%23%E3%81%B5%E3%81%8F%E3%81%B0%E3%81%AD%E3%81%A6%E3%81%99)

## コンテナ移行におけるアレコレと使えるアレコレ(仮)

[suginaga@SRE(@transnano)さん | Twitter](https://twitter.com/transnano)
ヤフー！

( 自分の資料をUPしたりしてたのであまりメモできず )

- Envoy
  - CentOS6, 7では動かない！
  - patch当てて動かしている人もいる

## わりとゴツいKubernetesハンズオンそのあとに

[Keita Mohri(@ktam1219)さん | Twitter](https://twitter.com/ktam1219)

Fusic！

- mockmockのPO!
- k8sは完全に理解している！
- Qiitaがばずった
  - [数時間で完全理解！わりとゴツいKubernetesハンズオン！！ - Qiita](https://qiita.com/Kta-M/items/ce475c0063d3d3f36d5d)
- 既存のDockerイメージしか使っていない
- オリジナルのアプリを作りたい
- [GoogleContainerTools/skaffold](https://github.com/GoogleContainerTools/skaffold)
- skaffold dev
  - ソースコード変更を検出してimageビルド、デプロイ
  - ローカルなのでimageのpushはfalse(不要)の設定をする
- skaffold run
  - 単発のデプロイ
- CI/CD向けに使う
  - imageのpushはtrueに設定する
  - CircleCI

## kubernetesのアップデートに関するあれこれ(仮)

@kyswtnbさん
 cacoo担当のSRE！


- kops?
  - k8sクラスタを管理するコマンド
  - AWSでは公式サポートしている
- ノードのカーネルのアップデート
  - MDS
    - 脆弱性
    - CPUの投機的実行に関するアレ
    - kernelアップデートが必要
    - kopsを使うとパッチが当たったカーネルを提供してくれる
  - TCP Snac
    - 脆弱性
  - いったんEC2で起動してカーネルバージョンをみてパッチが当たってるかを確認した
  - kops使うとクラスタのノードのカーネルアップデートを簡単にやってくれる
    - ちゃんとPodを追い出してくれながらノードのアップデートをやってくれる
- クラスタのアップデート
  - devなので気軽にあげてみたらこけた

## IstioによるTraffic Management

私の発表

https://speakerdeck.com/loftkun/traffic-management-with-istio
https://www.slideshare.net/ssuserb989ce/traffic-management-with-istio


## CNDT2019 見所をご紹介...???

うづらさん！

- Airbnb

- RoomA
- RoomB
  - Zラボ

## 反脆弱なシステムは目指してもいいものか？

[nwiizo(@nwiizo)さん | Twitter](https://twitter.com/nwiizo)

[can you aim for an anti-fragile system?](https://speakerdeck.com/nwiizo/can-you-aim-for-an-anti-fragile-system)

- フラジャイル
- ロバスト
- レジリエンス
