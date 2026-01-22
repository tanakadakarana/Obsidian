---
title: "AIとDB設計を考えてみた(前編) : マスタ管理はシングルテーブル設計+PostgreSQLがいいかもしれない"
source: "https://zenn.dev/ncdc/articles/e0475bcb5859f7"
author:
  - "[[Zenn]]"
published: 2026-01-11
created: 2026-01-22
description:
tags:
  - "clippings"
image: "https://res.cloudinary.com/zenn/image/upload/s--KczGnuSu--/c_fit%2Cg_north_west%2Cl_text:notosansjp-medium.otf_55:AI%25E3%2581%25A8DB%25E8%25A8%25AD%25E8%25A8%2588%25E3%2582%2592%25E8%2580%2583%25E3%2581%2588%25E3%2581%25A6%25E3%2581%25BF%25E3%2581%259F%2528%25E5%2589%258D%25E7%25B7%25A8%2529%2520%253A%2520%25E3%2583%259E%25E3%2582%25B9%25E3%2582%25BF%25E7%25AE%25A1%25E7%2590%2586%25E3%2581%25AF%25E3%2582%25B7%25E3%2583%25B3%25E3%2582%25B0%25E3%2583%25AB%25E3%2583%2586%25E3%2583%25BC%25E3%2583%2596%25E3%2583%25AB%25E8%25A8%25AD%25E8%25A8%2588%252BPostgreSQL%25E3%2581%258C%25E3%2581%2584%25E3%2581%2584%25E3%2581%258B%25E3%2582%2582%25E3%2581%2597%25E3%2582%258C%25E3%2581%25AA%25E3%2581%2584%2Cw_1010%2Cx_90%2Cy_100/g_south_west%2Cl_text:notosansjp-medium.otf_34:%25E3%2581%2584%25E3%2581%25B0%25E3%2582%2589%25E3%2581%258D%2Cx_220%2Cy_108/bo_3px_solid_rgb:d6e3ed%2Cg_south_west%2Ch_90%2Cl_fetch:aHR0cHM6Ly9zdG9yYWdlLmdvb2dsZWFwaXMuY29tL3plbm4tdXNlci11cGxvYWQvYXZhdGFyLzNhODZhNDA5ZDMuanBlZw==%2Cr_20%2Cw_90%2Cx_92%2Cy_102/g_south_west%2Ch_34%2Cl_default:og-publication-pro-mark-xcosax%2Cw_34%2Cx_217%2Cy_158/co_rgb:6e7b85%2Cg_south_west%2Cl_text:notosansjp-medium.otf_30:NCDC%2520%25E3%2583%2586%25E3%2583%2583%25E3%2582%25AF%25E3%2583%2596%25E3%2583%25AD%25E3%2582%25B0%2Cx_255%2Cy_160/bo_4px_solid_white%2Cg_south_west%2Ch_50%2Cl_fetch:aHR0cHM6Ly9saDMuZ29vZ2xldXNlcmNvbnRlbnQuY29tL2EtL0FPaDE0R2lXRjZXeUJCMTBrRDZNaV9Fa0tLQi13WFJSUC04eFlJbDV5eWljPXM5Ni1j%2Cr_max%2Cw_50%2Cx_139%2Cy_84/v1627283836/default/og-base-w1200-v2.png?_a=BACAGSGT"
---
[![](https://lh3.googleusercontent.com/a-/AOh14GiWF6WyBB10kD6Mi_EkKKB-wXRRP-8xYIl5yyic=s96-c)](https://zenn.dev/ibaraki)[いばらき](https://zenn.dev/ibaraki)

2026/01/11に公開

28

14%20%3A%20%E3%83%9E%E3%82%B9%E3%82%BF%E7%AE%A1%E7%90%86%E3%81%AF%E3%82%B7%E3%83%B3%E3%82%B0%E3%83%AB%E3%83%86%E3%83%BC%E3%83%96%E3%83%AB%E8%A8%AD%E8%A8%88%2BPostgreSQL%E3%81%8C%E3%81%84%E3%81%84%E3%81%8B%E3%82%82%E3%81%97%E3%82%8C%E3%81%AA%E3%81%84%EF%BD%9C%E3%81%84%E3%81%B0%E3%82%89%E3%81%8D&hashtags=zenn)%20%3A%20%E3%83%9E%E3%82%B9%E3%82%BF%E7%AE%A1%E7%90%86%E3%81%AF%E3%82%B7%E3%83%B3%E3%82%B0%E3%83%AB%E3%83%86%E3%83%BC%E3%83%96%E3%83%AB%E8%A8%AD%E8%A8%88%2BPostgreSQL%E3%81%8C%E3%81%84%E3%81%84%E3%81%8B%E3%82%82%E3%81%97%E3%82%8C%E3%81%AA%E3%81%84%EF%BD%9C%E3%81%84%E3%81%B0%E3%82%89%E3%81%8D)

[

![](https://storage.googleapis.com/zenn-user-upload/topics/43e28aa9cc.png)

PostgreSQL

](https://zenn.dev/topics/postgresql)[

![](https://storage.googleapis.com/zenn-user-upload/topics/f661d3909e.png)

Database

](https://zenn.dev/topics/database)[

![](https://static.zenn.studio/images/drawing/idea-icon.svg)

idea

](https://zenn.dev/tech-or-idea)

## はじめに

個人的にDBというものに対してあまり興味がありません。基本的にDB設計は詳しい人に任せたいと思っています。  
ですが、ある程度以上の大きめのシステムならそれで良いのですが、PoCやスモールスタートの場合だとDBだけを切り離せるほど人的リソースを割けないことも多いです。また、外部にDBを丸投げしたことにより知見がなくなり、DB起因でアプリの機能追加や変更が困難になるといった事態も避けたいです。  
なので、なるべくアプリ開発の邪魔にならないDB設計を考えておきたいなぁと、Geminiくん相手に壁打ちしてみました。

その結果、  
**硬い設計をするのが一般的なマスタ管理に柔軟性の高い「シングルテーブル設計」を採用し、NoSQLの定石である「シングルテーブル設計」をPostgreSQLのJSONB機能で実現するアプローチ**  
がGeminiくんとのやり取りの中で登場しました。今回はその内容を紹介したいと思います。  
前編では、マスタ管理の部分を書きます。

## モダンなアプリ開発に求められるDB設計は何か？

物事をわかりやすくするために、やりたいことをより具体化して整理しておきましょう。

- 柔軟でモダンなシステム
	- 前述の通り大規模なシステムはDBの専門家に任せたいので、規模は大きくないがモダンなシステムをなるべく柔軟に作ることを考えます
- 取り敢えずマスタを対象に考える
	- DB設計では、よくマスタとトランザクションに分けて考えると思いますので、まずはマスタについて考えてみます
- シンプルな構造を扱う
	- ユーザーの意見を素早く取り入れたいので、エクセルで作ったマスタ管理台帳を簡単に取り込めることを前提にしましょう
	- つまり人間が全体を管理できる程度にシンプルなマスタということです
- 自由度は高い
	- 項目の増減や変更の自由度は高くしたいです。モダンなアプリは変更に強いことが求められます

従来は多くのシステムのデータベースには、巨大なデータを扱える堅牢な設計を求められること多かったと思います。しかし、今は誰にでも気軽にアプリを開発してデプロイして公開できる時代です。モダンな開発では、規模は小さいけど柔軟性が求められる事が多く、従来のDB設計では上手くいかない事もあります。

そこで、従来のDB設計は一旦横において、エクセルで実施したマスタ定義をなるべくそのままシステム化することを考えてみました。

## テーブル設計を考える

では、どんな設計になるでしょうか。繰り返し書いている通り私自身はDB設計に対する興味がないので、自分で考えることは早々にあきらめてGeminiくんに考えてもらいました。便利な時代になりましたね。

### GeminiくんのDB設計

> 🤖Geminiくん : 今回のマスタ管理の着地点は、驚くほどシンプルです。マスタの定義をすべて一つのテーブルに集約します。

| カラム名 | 役割 |
| --- | --- |
| master\_type | カテゴリ、ステータスなどの区分（エクセルのシート名に相当） |
| code | 一意のキー |
| name | 表示名（実質的な Value） |
| category\_path | 文字列による階層表現（例：/家電/冷蔵庫） |
| metadata | エクセルの残りの列をすべてここに放り込む |

なんと、1つのテーブルに全ての項目を放り込むという大胆な設計を提案してきました。しかし、よく考えると実際にこれが理にかなっているのです。

### なぜこのシンプル構成がよい？

PoCやスモールスタートにおいて、従来の「1エンティティ＝1テーブル」という硬い設計は、柔軟な開発の「足枷」になります。エクセルの管理台帳に1つ列を足したいだけなのに、DBのマイグレーション（ALTER TABLE）に怯え、影響調査に時間を費やすことになります。  
そこでまずは、テーブルを細かく分けず、あらゆるマスタを一つの大きな器に放り込む **「シングルテーブル設計」** を選択肢に加えます。これにより、構造を固定せず、ビジネスの変化（エクセルの変更）をそのまま受け止める構成を考えることが出来ます。

例えるなら、正規化重視の設計は川の流れをガチガチに固める「堤防」を作るのに対して、シングルテーブル設計は広い「遊水地」を用意するといったところでしょうか。

### シングルテーブル設計をPostgreSQLで実装する

「シングルテーブル」と聞くと、DynamoDBのようなNoSQLを連想する方が多いでしょう。実際、クエリの効率化のためにデータを1つのテーブルに集約する手法はNoSQLの定石です。  
DynamoDBでは、パーティションキー（PK）やソートキー（SK）を抽象的に定義することで、後からアプリ側でデータを解釈する柔軟性を持たせることが一般的です。しかし、ここで直面するのは「検索」の壁です。  
DynamoDBは一部の項目にしかインデックスを作れないですし、それを補うGSIなどの機能はとても複雑です。  
今回は対象がマスタ管理ですので、検索の柔軟性はとても重要です。  
そこでシングルテーブル設計によるマスタ管理を、検索能力が高いPostgreSQLで実施することを考えてみましょう。

- アドホックな検索への対応力
	- NoSQLは、事前に定義したアクセスパターンには強いですが、想定外の条件での検索や集計（OLAP的用途）は苦手
	- PostgreSQLは、SQLの強力な表現力で、いつでも自由な切り口でデータを抽出できる
- JSONBと高度なインデックス
	- PostgreSQLのJSONB型はスキーマレスな柔軟性を提供
	- 内部フィールドに対してGIN（全文検索的インデックス）やB-Treeインデックスを後から自由に追加可能
- 複雑な階層・パス検索
	- 「/食品/生鮮/野菜」のようなパスに基づく検索は、PostgreSQLのLIKE検索やltree型を使えば、インデックスを効かせつつ爆速実行可能
	- NoSQLのキー設計で解決するよりも遥かに直感的で強力

このようにPostgreSQLをただのRDBではなく **「強力な検索エンジンを備えたドキュメント・ストア」** として使うことで、スマートなマスタ定義の管理が実現できます。

## マスタのデータを如何に取得するのか？

このDB定義に対して「テーブルが1つでリレーションもないなら、アプリ側で扱うときに不便じゃない？」と思われるかもしれません。  
実はそんなことはありません。「DB側でJOINして整える」のではなく、「DB側で構造化（JSON化）して1発で返す」というアプローチを取りましょう。

PostgreSQLには `json_agg()` や `jsonb_build_object()` といった、抽出結果をまるごと構造化する強力な関数があります。これらを使えば、複数テーブルを何度も叩く代わりに、必要なマスタを1つのJSONオブジェクトとしてアプリに返すことができます。アプリ側はそれを受け取り、起動時や定期的なリフレッシュのタイミングでメモリ上に展開してしまえばいいのです。

- アプリ起動時に全ロード
- メモリ上で高速検索
- DB通信のオーバーヘッドなし

「マスターのデータを全て渡すのは無駄じゃないのか？」と思われるかもしれません。しかし、今回はあくまでエクセルで人間が管理できるマスタであることが前提です。今時のコンピューターやネットワークなら数千件・数万件程度のデータは一瞬で処理出来ます。  
むしろ通信が1回で完結するので効率よくデータを処理することが可能です。  
このように「DBに知能を持たせる」のをやめ、アプリが使いやすい「塊」としてデータを扱う。こうすることで、リレーションに頼らないスマートなマスタ取得が実現できます。

## DBをガチガチに固めるのはモダンな開発にマッチしない

従来のアプリ開発では、特にマスタに関しては整合性を徹底するためにDBの型や制約をガチガチに固めることが多いです。  
しかし、素早い開発や柔軟な仕様変更を求められるモダンな開発では、この設計が足枷になってしまうことが多々あります。  
DBは「器」であって「フィルター」ではありません。JSONBで何でも受け入れる「柔軟な土台」に徹し、データの解釈や不整合の吸収は、変更が容易なアプリ側で対応することも考えるべきです。  
アプリが賢く立ち回ることで、土台であるDBを自由にする。この関係性こそが、モダンな開発における健全なアプリとDBの関係ではないでしょうか。

## おわりに+次回予告

このようにPostgreSQLを使ってマスタ定義を自由にすることで、柔軟なアプリ開発を爆速で実現出来ます。

と言いたいところですが、「そんなルーズなマスタではトランザクションの整合性が取れないのでは？」という疑問がでるのは当然でしょう。また「小規模アプリと言っているけど、将来的にマスタが巨大化すると詰むよね？」と思うかもしれません。  
後編ではこの「ルーズなPostgresql」を支える「整合性を担保するDynamoDB」について語ります。

<iframe id="zenn-embedded__5e8accdde4de5" src="https://embed.zenn.studio/card#zenn-embedded__5e8accdde4de5" data-content="https%3A%2F%2Fzenn.dev%2Fncdc%2Farticles%2F102097eda167ba" frameborder="0" scrolling="no" loading="lazy" height="122"></iframe>

[![](https://storage.googleapis.com/zenn-user-upload/avatar/3a86a409d3.jpeg)](https://zenn.dev/p/ncdc)

NCDC テックブログ により固定

NCDCでは、一緒に働いてくれるメンバーを通年で募集しています。  
詳しくは下記をご覧ください。

- [NCDC公式ホームページ](https://ncdc.co.jp/)
	- [採用ページ](https://ncdc.recruit-site.biz/)
- [エンジニア向け採用情報](https://ncdcdev.github.io/recruitment/)
- [Green](https://www.green-japan.com/company/5693)
- [Findy](https://findy-code.io/companies/2634)

28

14%20%3A%20%E3%83%9E%E3%82%B9%E3%82%BF%E7%AE%A1%E7%90%86%E3%81%AF%E3%82%B7%E3%83%B3%E3%82%B0%E3%83%AB%E3%83%86%E3%83%BC%E3%83%96%E3%83%AB%E8%A8%AD%E8%A8%88%2BPostgreSQL%E3%81%8C%E3%81%84%E3%81%84%E3%81%8B%E3%82%82%E3%81%97%E3%82%8C%E3%81%AA%E3%81%84%EF%BD%9C%E3%81%84%E3%81%B0%E3%82%89%E3%81%8D&hashtags=zenn)%20%3A%20%E3%83%9E%E3%82%B9%E3%82%BF%E7%AE%A1%E7%90%86%E3%81%AF%E3%82%B7%E3%83%B3%E3%82%B0%E3%83%AB%E3%83%86%E3%83%BC%E3%83%96%E3%83%AB%E8%A8%AD%E8%A8%88%2BPostgreSQL%E3%81%8C%E3%81%84%E3%81%84%E3%81%8B%E3%82%82%E3%81%97%E3%82%8C%E3%81%AA%E3%81%84%EF%BD%9C%E3%81%84%E3%81%B0%E3%82%89%E3%81%8D)

[![いばらき](https://lh3.googleusercontent.com/a-/AOh14GiWF6WyBB10kD6Mi_EkKKB-wXRRP-8xYIl5yyic=s96-c)](https://zenn.dev/ibaraki)

[いばらき](https://zenn.dev/ibaraki)

いばらきです / NCDCという会社で働いています / AWS SAP, DOP / GoogleCloud PCA / AWS Amplify Gen2本を書きました→[amazon.co.jp/dp/B0G1LTHVQD/](https://www.amazon.co.jp/dp/B0G1LTHVQD/)[![NCDC テックブログ](https://storage.googleapis.com/zenn-user-upload/avatar/3a86a409d3.jpeg)](https://zenn.dev/p/ncdc)

[NCDC テックブログ](https://zenn.dev/p/ncdc)

NCDC株式会社( [ncdc.co.jp/](https://ncdc.co.jp/) )のテックブログです。 主にエンジニアチームのメンバーが投稿します。 募集中のエンジニアのポジションや、採用している技術スタックの紹介などはこちら( [github.com/ncdcdev/recruitment](https://github.com/ncdcdev/recruitment) )をご覧ください！