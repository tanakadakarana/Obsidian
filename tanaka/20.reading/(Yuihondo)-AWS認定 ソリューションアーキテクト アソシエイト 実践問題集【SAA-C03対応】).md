---
kindle-sync:
  bookId: '18517'
  title: AWS認定 ソリューションアーキテクト アソシエイト 実践問題集【SAA-C03対応】 (唯本堂 (Yuihondo))
  author: 唯本堂 (Yuihondo)
  asin: B0F6S6C449
  lastAnnotatedDate: Invalid date
  bookImageUrl: 'https://m.media-amazon.com/images/I/71ZIoc3c55L._SY160.jpg'
  highlightsCount: 15
---
# AWS認定 ソリューションアーキテクト アソシエイト 実践問題集【SAA-C03対応】)
## Metadata
* Author: [唯本堂 (Yuihondo)](https://www.amazon.comundefined)
* ASIN: B0F6S6C449
* Reference: https://www.amazon.com/dp/B0F6S6C449
* [Kindle link](kindle://book?action=open&asin=B0F6S6C449)

## Highlights
問題3 あなたの会社では、医療データを収集するアプリケーションが複数のAmazon EC2インスタンス上で稼働しています。これらのインスタンスはAmazon VPC内にあり、収集したデータをインターネットを経由せずにAmazon DynamoDBへ安全に送信する必要があります。これを実現するための最適な方法はどれでしょうか？ — location: [47](kindle://book?action=open&asin=B0F6S6C449&location=47) ^ref-21768

---
b. DynamoDBのVPCゲートウェイエンドポイントを作成し、ルートテーブルを設定する — location: [51](kindle://book?action=open&asin=B0F6S6C449&location=51) ^ref-4775

---
解説: Amazon DynamoDBへのインターネットを経由しないプライベートアクセスは、VPCゲートウェイエンドポイントを作成し、VPCのルートテーブルを設定することで実現します。これにより、インスタンスからDynamoDBへの安全でプライベートな通信が可能になります。 — location: [55](kindle://book?action=open&asin=B0F6S6C449&location=55) ^ref-45948

---
b. Amazon SQS FIFO キューを利用してメッセージを順序通りに配信し、Lambda で処理する — location: [67](kindle://book?action=open&asin=B0F6S6C449&location=67) ^ref-56945

---
Amazon SQS FIFO キューは、First-In-First-Out の順序を保証しながら、最大3,000件/秒のスループット（バッチ時）で処理できる。 — location: [71](kindle://book?action=open&asin=B0F6S6C449&location=71) ^ref-38991

---
問題5 政府機関が、セキュリティ上の理由からインターネットを通さずに庁舎内の大量の履歴文書データを Amazon S3 に移行しようとしています。専用線（AWS Direct Connect）をすでに導入済みで、可用性と自動化を重視したいと考えています。最も適したサービスはどれですか？ — location: [77](kindle://book?action=open&asin=B0F6S6C449&location=77) ^ref-16888

---
b. AWS DataSync をエージェント経由で構成し、VPC エンドポイントを通じてアップロードする — location: [81](kindle://book?action=open&asin=B0F6S6C449&location=81) ^ref-24853

---
解説： DataSync はオンプレミスと AWS の間での大量データ転送に最適。VPC エンドポイントを通すことでプライベート経路を確保できます。 — location: [84](kindle://book?action=open&asin=B0F6S6C449&location=84) ^ref-35405

---
問題6 法律事務所が、機密性の高い証拠文書を Amazon S3 にアップロードするクラウドシステムを構築中です。セキュリティチームは「データがインターネット経由で送信される前にすでに暗号化済みであること」を厳格に求めており、クラウド上での暗号処理は一切認められていません。 この要件を最も確実に満たすアプローチはどれですか? — location: [89](kindle://book?action=open&asin=B0F6S6C449&location=89) ^ref-35895

---
a. クライアント側でデータを暗号化し、暗号鍵はAWS KMSで管理する — location: [93](kindle://book?action=open&asin=B0F6S6C449&location=93) ^ref-45817

---
解説: クライアント側暗号化（CSE）を実施し、AWS KMS のカスタマーマネージドキーで暗号鍵を安全に保管・制御する構成は、「アップロード前に完全に暗号化されている」ことを満たしつつ、鍵管理の効率性も両立できます。 — location: [97](kindle://book?action=open&asin=B0F6S6C449&location=97) ^ref-4526

---
a. サービスAがデータをAmazon SQSに送信し、サービスBがSQSから取り出して処理する — location: [107](kindle://book?action=open&asin=B0F6S6C449&location=107) ^ref-47314

---
Amazon SQS はメッセージングベースの非同期通信を可能にするサービスであり、処理の遅い配送管理を独立してスケーリングできます。サービス間の結合度を下げつつ、高い可用性を確保できます。 — location: [112](kindle://book?action=open&asin=B0F6S6C449&location=112) ^ref-16698

---
問題9 ある多国籍企業では、各国に分散する支社の財務データを Amazon Aurora を用いて一元管理しています。地政学的リスクの影響を考慮し、メインリージョンに障害が発生した場合でも即座に別リージョンで処理を継続できるようにしたいと考えています。要件として、データ損失は1秒未満（RPO）、復旧時間は1分未満（RTO）を保証する必要があります。 — location: [132](kindle://book?action=open&asin=B0F6S6C449&location=132) ^ref-17294

---
a. Amazon Aurora Global Database を使用し、各リージョンに読み取り専用レプリカを配置する — location: [137](kindle://book?action=open&asin=B0F6S6C449&location=137) ^ref-36339

---
