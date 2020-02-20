# OpenShift Meetup Fukuoka サテライト (Tokyo #7)

2019/10/18 Fri

リージャス アクア博多ビジネスセンター

ハッシュタグ [#openshiftjp](https://twitter.com/search?q=%23openshiftjp)


## 会場案内・OpenShift JP/OpenShift New Topicのご紹介

- OpenShift 4.2がavailableになったよ

## ここまでデキるOpenShift Service Mesh!!

英語だーー！！

- Istioの話
- 
- 
- 
- 

## Knative Servingのイマ

- Serving
- Eventing
  - イベント駆動でアプリを動作させるためのフレームワーク

- 
- 
- 
- 

## 分散トレーシング

- トレーシングの歴史
  - Open Tracing
    - CNCF
    - Tracing APIの仕様を定める
    - Zipkin, Jeager,,
    - Tracingのみを提供
    - 11/6に終了
  - OpenCensus
    - Googleが社内で使用している
    - TracingだけでなくMetricも含む
    - 11/6に終了
- OpenTelemetry
  - CNCF
  - OpenTracingとOpenCensusが合体
- なぜ分散トレーシングが重要なのか
  - ログとメトリック収取だけでは困難
- 分散トレーシング
  - サービス間のリクエストの詳細な状態を記録する
  - 複雑なマイクロサービス間の関係をビューで確認できる
- 用語の整理
  - Trace
    - Spanで構成される
  - Span
    - 名前と時間を持つ、親子関係を持つ
  - Root Span
    - 最初のSpan
  - Context Propagation
    - Tracingはコンテキストの伝搬で成り立つ
      - 複数サービスを横断するリクエストを一意に識別
  - Tracer Interface
    - 
- 分散トレーシングの概念
- Spanのフォーマット
- Tracing実装
  - Zipkin
    - OpenTraicingの実装の1つ
    - Twitterが開発
  - Jaeger
    - OpenTraicingの実装の1つ
    - Uberが開発
    - OpenTelemetryと少しずつ統合していくと思われる
  - 

BookInfo
- [Search · X-Request-Id](https://github.com/istio/istio/search?q=X-Request-Id&type=Code)
- [Search · opencensus](https://github.com/istio/istio/search?q=opencensus&unscoped_q=opencensus&type=Code)

## ServiceMesh LT大会


## Closing お片付け&撤収
