# 【福岡】SmartNews Tech Night in Fukuoka Vol.1

2019/05/28 Tue

スマートニュース株式会社福岡オフィスさんにて

ハッシュタグ [#SN_technight](https://twitter.com/search?q=%23SN_technight)

![](https://pbs.twimg.com/media/D7pTV5HUwAAJkqL.jpg:large)


## サーバサイドの技術スタック・アーキテクチャ総ざらい

- Java Spring Boot
- コンテナはECS
- itamae(chefみたいなやつ)
- 監視・通知
  - Datadog, PagerDuty
  - Runscope
  - New Relic

- ニュース配信基盤が扱うデータトラフィックの規模
  - CDN(Akamai)
    - 480k+ hits/second

- Onlineのアーキテクチャ
  - in-memory data gridを採用し高速化
    - Hazelcast cluster

- We are hiring!
  - フリーアドレス
  - 住宅手当
　- etc

## Unshackling the database! Using Redis as the primary data storage to ensure rapid growth scalability ※通訳あり

マークさん

- 日本には3年在住
- SmartNewsに入って3ヶ月
- Agenda
  - Project case study
  - Workflow

- A/B test System
- Use Cases
  - 1 create new tests
  - 2 fetch test identifiers
  - 3 analize test results
- Quality Attributes
  - Performance
    - 200ms response time
  - Scalability
    - 30k+ req/sec
    - 1.5M+ unique users
  - Availability
    - 99.99%
- Analysys
  - Current Architecture
    - アプリはDB書き込み処理終わるまで待たされる
    - DBはmasterが多い(API, Adimin,,,)
  - SProposed Architecture
    - アプリ DB間にCacheを置いた
      - CacheにはRedisが向いてそう
- Tech Stack
  - Kotlin
  - Coroutines
  - Spek Framework
  - Spring Boot 2
- Canary Deployment
  - New Relic
- Outcome
  - slached peak res time by up to 50%
  - Removed rate limiting database protection

## 質問タイム

- エンジニアの割合
  - 日本とUS含めて60弱
  - SREチームは3人
    - 7, 8月に1人ずつ入社予定
- SmartNewsのアクセスパターン
  - ほとんどのユーザは日本から

## 懇親会

