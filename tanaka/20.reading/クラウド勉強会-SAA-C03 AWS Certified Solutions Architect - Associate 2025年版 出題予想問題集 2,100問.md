---
kindle-sync:
  bookId: '43381'
  title: >-
    SAA-C03: AWS Certified Solutions Architect - Associate 2025年版 出題予想問題集
    2,100問: AWS 認定 SAA-C03に対応　スマホで便利な一問一答形式　理解が深まる要点整理表つきの解法解説
  author: クラウド勉強会
  asin: B0F9B6QM5P
  lastAnnotatedDate: Invalid date
  bookImageUrl: 'https://m.media-amazon.com/images/I/61yLylre3qL._SY160.jpg'
  highlightsCount: 20
---
# SAA-C03: AWS Certified Solutions Architect - Associate 2025年版 出題予想問題集 2,100問
## Metadata
* Author: [クラウド勉強会](https://www.amazon.comundefined)
* ASIN: B0F9B6QM5P
* Reference: https://www.amazon.com/dp/B0F9B6QM5P
* [Kindle link](kindle://book?action=open&asin=B0F9B6QM5P)

## Highlights
Amazon SQS の FIFO キュー — location: [21](kindle://book?action=open&asin=B0F9B6QM5P&location=21) ^ref-29792

---
Amazon SQS FIFO キュー あり（厳密） 順序が重要なメッセージング、一度だけの処理が必要な場合 — location: [36](kindle://book?action=open&asin=B0F9B6QM5P&location=36) ^ref-31163

---
データベース認証情報をAWS Secrets Managerに保存し、ウェブサーバーにSecrets Managerへのアクセス権限を付与する — location: [54](kindle://book?action=open&asin=B0F9B6QM5P&location=54) ^ref-44168

---
解説 AWS Secrets Managerは、データベース認証情報、APIキー、その他のシークレットを安全に保存、管理、取得するためのサービスです。 — location: [59](kindle://book?action=open&asin=B0F9B6QM5P&location=59) ^ref-23851

---
AWS KMSは暗号化キーの管理サービスであり、認証情報の自動ローテーションには対応していません。 — location: [68](kindle://book?action=open&asin=B0F9B6QM5P&location=68) ^ref-11486

---
Amazon S3でELBログファイルを保存し、Amazon EMRでログファイルを分析する — location: [90](kindle://book?action=open&asin=B0F9B6QM5P&location=90) ^ref-1641

---
ALBのログは、デフォルトでAmazon S3バケットに保存でき — location: [96](kindle://book?action=open&asin=B0F9B6QM5P&location=96) ^ref-56881

---
ログ分析には、大規模データ処理に特化したマネージドサービスであるAmazon EMR（Elastic MapReduce）が最適です。 — location: [97](kindle://book?action=open&asin=B0F9B6QM5P&location=97) ^ref-27875

---
DynamoDBはNoSQLデータベースであり、ログファイルの保存には最適化されていません — location: [100](kindle://book?action=open&asin=B0F9B6QM5P&location=100) ^ref-14332

---
S3とEMRの組み合わせは、大規模なログデータの保存と分析に最適なソリューションを提供します。 — location: [115](kindle://book?action=open&asin=B0F9B6QM5P&location=115) ^ref-32522

---
Transit Gatewayを作成し、すべてのVPCのサブネットにアタッチメントを配置して、Transit Gatewayルートテーブルに新しいルートを設定する — location: [124](kindle://book?action=open&asin=B0F9B6QM5P&location=124) ^ref-2349

---
1,000以上のVPC間の通信を効率的に実現する方法を問われています。 AWS Transit Gatewayは、VPCとオンプレミスネットワークを接続するためのハブとして機能するサービスです。多数のVPC間の接続を簡素化するために設計されており、スケーラブルなネットワークアーキテクチャを実現します。Transit Gatewayを使用すると、すべてのVPCを一つの中央ハブに接続するだけで、VPC間の通信が可能になります。 — location: [130](kindle://book?action=open&asin=B0F9B6QM5P&location=130) ^ref-44958

---
接続方法 大規模VPC接続の適合性 管理の複雑さ スケーラビリティ Transit Gateway 高 低 高 — location: [142](kindle://book?action=open&asin=B0F9B6QM5P&location=142) ^ref-38532

---
Transit Gatewayは、大規模なVPC接続シナリオ向けに特別に設計されており、集中管理、簡素化されたルーティング、高いスケーラビリティを提供するため、この要件に最適なソリューションです。 — location: [148](kindle://book?action=open&asin=B0F9B6QM5P&location=148) ^ref-12294

---
Amazon SQSを使用してアプリケーション層とデータベース層を分離し、キューから — location: [164](kindle://book?action=open&asin=B0F9B6QM5P&location=164) ^ref-59981

---
データベースにアイテムを書き込むAWS Lambda関数を設定する — location: [165](kindle://book?action=open&asin=B0F9B6QM5P&location=165) ^ref-42116

---
ソリューション データモデル変更 データ損失防止 予測不可能なトラフィック対応 SQS + Lambda 不要 キューによるバッファリング 非同期処理で対応可能 DBインスタンスのスケールアップ 不要 スケーリング中にリスクあり 予測が難しく対応困難 ElastiCache for Memcached 不要 キャッシュのみで保証なし キャッシュヒット時のみ効果的 Aurora PostgreSQL + リードレプリカ 互換性あり 書き込みは単一インスタンスに依存 読み取りのみスケール可能 SQSを使用したデカップリングは、AWS Well-Architected Frameworkの信頼性の柱に沿ったアプローチであり、予測不可能な負荷に対して堅牢なシステムを構築するためのベストプラクティスです。 — location: [182](kindle://book?action=open&asin=B0F9B6QM5P&location=182) ^ref-52462

---
AWS VPN CloudHubは、複数のサイト間を接続するためのハブアンドスポークモデルを提供するサービスです。既存のVPN接続を活用して、リモートオフィス間の通信を低コストで実現できます。 — location: [235](kindle://book?action=open&asin=B0F9B6QM5P&location=235) ^ref-40204

---
Amazon SNSトピックを作成し、2つのAmazon SQSキューがそのトピックをサブスクライブするよう設定する。Amazon S3にAmazon SNSへの通知送信権限を付与し、バケットが新しいSNSトピックを使用するように更新する。 — location: [267](kindle://book?action=open&asin=B0F9B6QM5P&location=267) ^ref-57690

---
2つのAmazon SQSキューがそのトピックをサブスクライブするよう設定 — location: [272](kindle://book?action=open&asin=B0F9B6QM5P&location=272) ^ref-44074

---
