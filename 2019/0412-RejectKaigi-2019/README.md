# RejectKaigi 2019 福岡会場 (a.k.a. Fukuoka.rb #131)

2019/04/12 Fri

GMOペパボ 福岡支社さんにて

ハッシュタグ [#rubykaigi](https://twitter.com/search?q=%23rubykaigi)

![](https://pbs.twimg.com/media/D38k2UPU8AAu5Ko.jpg:large)

## 開会の挨拶

- 今シーズン初の4トラック！
- rejectされた発表を供養
- 乾杯！

## OCI-compatible haconiwa ─ hurdles and advantages ─ もしくはOCI interefaceを持つRuby processについて

- 渋谷道玄坂のビルの人
- cashというサービス出している
- コンテナってdockerだよね
  - docker以外の選択肢が選ばれない理由
    - installしやすい
    - 有名だから
- before docker
  - LXC
- after docker
  - cri-1
  - Kata Container
- OCI
  - コンテナの規格を取りまとめて出している
  - Image Spec
  - Runtime Spec
- CRI and Kubernetes world
  - kubelet --- CRI protobuf --- CRI --- container
  - CRI compatibleならばkubeletのbackendとして使える
  - OCI compatible
- Why CRI-compatible ？
  - How to implement CRI
- OCI specification and haconiwa
  - image spec
  - runtime spec
    - うづらさんが2016年にブログにまとめている
      - [OCI Runtime Specification を読む - ローファイ日記](https://t.co/iE5JSW2ySB)
- conclusion
  - OCI対応したい、に興味がある

## Agyoh and Umgyo Assume Controll of a Mobile Device


LT枠はAcceptされました！
40分枠はNot Acceptでした、供養します

- Agyoh
  - pushサーバ
- Umgyo
  - クライアント
- 金剛力士が由来

