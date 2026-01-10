---
title: "Obsidian × NotebookLM × Antigravity｜FURUYA"
source: "https://note.com/fryx404/n/n0ff98fb4a3d0"
author:
  - "[[FURUYA]]"
published: 2026-01-03
created: 2026-01-10
description: "おはようございます。furuya (@fryx404) です。  今回は、私が最近構築している「セカンドブレイン」の環境について紹介したいと思います。 Obsidianをハブにして、話題の NotebookLM や Antigravity を組み合わせた構成です。 結構洗練られてきたので一旦このへんで公開してみようかなという感じです。よろしくお願いします！  セカンドブレイン｜FURUYA｜noteObsidianやNotion、考え方などnote.com   Obsidianのセットアップ  まずは母艦となるObsidianのセットアップから。 特に変わっ"
tags:
  - "clippings"
---
![見出し画像](https://assets.st-note.com/production/uploads/images/241019073/rectangle_large_type_2_4f0375d4263750c640f468bc58633c0e.png?width=1280)

## Obsidian × NotebookLM × Antigravity

[FURUYA](https://note.com/fryx404)

おはようございます。 **furuya (**[**@fryx404**](https://x.com/fryx404)**)** です。

今回は、私が最近構築している「セカンドブレイン」の環境について紹介したいと思います。  
Obsidianをハブにして、話題の NotebookLM や Antigravity を組み合わせた構成です。  
結構洗練られてきたので一旦このへんで公開してみようかなという感じです。よろしくお願いします！

[**セカンドブレイン｜FURUYA｜note** *ObsidianやNotion、考え方など* *note.com*](https://note.com/fryx404/m/mc315c5dab73b)

## Obsidianのセットアップ

まずは母艦となるObsidianのセットアップから。  
特に変わったことはしていませんが、 **「シンプル」** であることを心がけています。

![画像](https://assets.st-note.com/img/1767414332-HefiKYXIPZu3xtUkzwdTmph4.png?width=1200)

私のObsidianの画面

### Basesで自分を管理する

まずは多くのObsidianユーザーが使用しているデイリーノートの紹介です。  
私のデイリーは3段階の構想になっていて、一番上が「ハビットトラッカー」、中断が「ジャーナル」、下段が「タイムスタンプ」となっています。

![画像](https://assets.st-note.com/img/1767413801-c4PAXniN2F6sboeKC85l7q0g.png?width=1200)

デイリーの中身

ハビットトラッカーはYAMLフロントマター、プロパティで管理しています。  
天気や体調を記載したり、チェックボックスでワークアウトを記録したり、といった感じです。  
こうしておけば、コアプラグインのBases で一覧表示することができます。（Notionみたいな感じ）

![画像](https://assets.st-note.com/img/1767414198-W9kmEncKvjpIuoyzMs8BQdX6.png?width=1200)

Basesで一覧表示ができる

中断以降、つまりノートの本文のところでは、その日の気付きやメモをジャーナリングしておきます。  
まぁ正直なんにもない日もあります（というかそっちのほうが多いかも？）  
無理に書こうとせず欲しいときに欲しいだけ書く、それだけで十分なんですよ。

下段のタイムスタンプについて、これはもうみんな知っている超有名プラグイン「Thino」を使ったライフログです。  
ThinoはXみたいな感じで、つぶやくみたいにメモができるプラグインです。  
Thinoに呟けばデイリーに勝手に記載されるので、本当につぶやき感覚で投稿しています。

![画像](https://assets.st-note.com/img/1767414559-tFOvSwPpK4dXoVm9AQyrubZC.png?width=1200)

Thinoでタイムスタンプ作成

ハビットトラッカー、ジャーナル、ライフログ、タイムスタンプ、全てをデイリーノート内に記載して、その日の健康状態、習慣化の記録、思考の断片が全て一つのノートで完結するようにしています。  
これを実践してまだ1ヶ月ほどですが、続けていけば年間365ページのライフログが完成します。  
このログの活用方法は後ほど！

![画像](https://assets.st-note.com/img/1767415194-nZaMoJRcUNi1ShfVjwy57P8E.png?width=1200)

デイリーノートまとめ

  

### タグは最小限に

情報の整理において、タグは極力最小限に抑えています。  
私のタグ構成は「dairy」 「monthly」 「src」 「status」 の4つだけです。

srcはSourceの略で、情報のソース（情報源）を示しています。  
ウェブクリップなのか、メルマガなのか、本なのかYoutubeなのかといった感じです。  
例えばウェブの情報源は遮断して、本から得た知識だけをフィルターしたい、といったときに使います。

![画像](https://assets.st-note.com/img/1767414953-UOXWLyhYDwpec1aHjNg89Qoz.png?width=1200)

statusは「not\_started（未着手）」「in\_progress（進行中）」「complete（完了）」の3つのステータスで管理しています。  
これは主にnoteの記事を書くときや、このあと説明するMOC（Map of Content）の構築で使用しています。  
ステータスをタグ管理しているのは、フォルダを横断してBasesで一覧表示することができるからです。

![画像](https://assets.st-note.com/img/1767415138-K9wZdjOF6s2DCvHh1acxV7B3.png?width=1200)

Basesでステータスを管理

タグの数を絞っているのは、 **MOC（Map of Content）** をしっかり組むことで管理するスタイルを目指しているからです。  
MOCは簡単に言うとリンク集です。  
\[\[ファイル名\]\] でノート内にリンクを張り、リンク集を作ります。  
直訳すると「コンテンツの地図」となり、膨大なメモの中から道しるべを示すことができます。

例えば、「3DCG基礎」といったノートを作成して、その中にリンクを挿入します。  
タグではなくノートなので、並び替えや重要度の順序を入れ替えることもできるし、学習のロードマップを作成することもできます。  
知識は蓄えるだけではもったいなく、MOCを構築するときには確実にリンク先のメモを読まないといけないし理解していないと構築できないはずです。  
このひと作業を行うことで理解を深めてアウトプットにつなげることができます。

![画像](https://assets.st-note.com/img/1767415641-3tNkAp6DV7KzvHwau2TCbI5n.png?width=1200)

MOCの例

私の場合は更に、MOCをタグのように使う、といったこともやっています。  
本やエッセイの著者のMOCを作成したり、BlenderやPythonといったMOCも作成しています。  
タグとの決定的な違いは「メタデータ」か「実態」か、でしょうか。  
タグは検索して並べるだけでタグ自体にメモはかけませんよね。MOCは言ってしまえばただのノートなので好き放題こねくり回すことができます。

![画像](https://assets.st-note.com/img/1767415831-OhnXimSbsf0eQ8ox7laKz9Pw.png?width=1200)

MOCのタグ化

[Capacities](https://capacities.io/) というオブジェクト指向のノートアプリがあるのですが、考え方はこれに近いと思っています。  
Notionのリレーションでタグ管理する運用なども行っていて、慣れるとこれじゃないとしっくりこないです。  
ぜひ皆さんもお試しあれ。

![画像](https://assets.st-note.com/img/1767415691-a6WId9HMvX0EUqLZNzKpcj3w.png?width=1200)

タグとMOCまとめ

  

### Canvasで知識を再構築する

インプットの深堀りにはコアプラグインの Canvas を利用しています。  
Canvasは超ざっくり説明すると、ホワイトボード上にメモを配置することができるものです。  
ウェブクリップした記事をCanvasに配置すると、記事の最初から最後までを巻物のように伸ばして貼り付けることができます。これを利用すれば深堀りしたいところにメモを追加することができるというわけです。

![画像](https://assets.st-note.com/img/1767416148-DNu6xH5j8m7YGL0no2vcw9qA.png?width=1200)

Canvasの例

他にもマインドマップのような使い方できるので、1つの問いから知識を深めていくこともできます。  
これはもはやマークダウンテキストエディタの枠を超えて、視覚的に情報を「再構築」することができるかなり強いプラグインと言えると考えます。

このように私はObsidianで、デイリー、ジャーナル、ライフログ、クリップなどあらゆる情報を一元管理したうえで、BasesやCanvasで深堀り分析ができるシステムを構築しています。

![画像](https://assets.st-note.com/img/1767416182-J6WmaxnioENvMPyCFQf72tHz.png?width=1200)

Canvasまとめ

  

### Obsidian × NotebookLM

さてここからは蓄えた情報をどう分析するのかという話になってきます。  
先程伝えたように、私のデイリーノートの中身は健康管理記録、ハビットトラッカー、ジャーナル、ライフログなど多岐にわたっています。もっというと体重の推移やその日の天気なんかも入力しています。  
これ記録してなんか意味があるのか？と思うかもしれません。  
でも大丈夫、意味あるんです。

Obsidianはローカルのファイル管理にこだわっていますよね。  
皆さんのパソコン、スマホの中にはObsidianのVaultがあり、その中にはmdファイルがあります。  
このmdのファイル、Obsidian以外でも利用することができます。

![画像](https://assets.st-note.com/img/1767416340-XQFcnvuymg3EdzbVJTZHLCtP.png?width=1200)

MDファイルは自身のローカルストレージに存在している

[NotebookLM](https://notebooklm.google.com/) はご存知でしょうか？  
AIを搭載したリサーチ・アシスタントサービスで、PDFやウェブサイトを読み込ませたうえでその読み込ませた情報だけを基に要約、分析、質問応答などを行うことができるツールです。  
これにmdファイルを読み込ませることで、自己分析が可能となるわけです。

例えばなんか体調が悪いな、と思ったときに最近の睡眠スコアや天気、ライフログの行動記録から因果関係を推察することができます。  
それだけではなく、NotebookLMのStudio機能を利用すれば、マインドマップの作成、レポートの作成といったことができます。

![画像](https://assets.st-note.com/img/1767416521-75sGVPETf3uXjYHZ9U8qxyK6.png?width=1200)

NotebookLMのレポートサンプル

デイリーの分析以外にも、学習ログなどをObsidianで記録している場合はそのmdファイルを読み込むことで、フラッシュカードやテストも行えます。  
NotebookLMはめちゃくちゃObsidianと相性のいいサービスなのでおすすめです。

![画像](https://assets.st-note.com/img/1767416383-Od8lMTZ4vryWbChURHQY0Ve2.png?width=1200)

Obsidian × NotebookLMまとめ

  

### Obsidian × Antigravity

次に、メモの整理と執筆のサポートとして Antigravityを紹介します。

[**Google Antigravity** *Google Antigravity - Build the new way* *antigravity.google*](https://antigravity.google/)

がその前に、Obsidian in Cursorはご存知でしょうか？  
昨年一斉を風靡したObsidianとAI搭載コードエディタの最適解です。  
Antigravityはほとんどそれだと思ってください。

AntigravityというのはGoogleが作成したCursorみたいなものです。  
ではCursorで良くないか？という疑問が湧いてくると思います。  
はい、Cursorでもいいです。

今回はNotebookLMとAntigravityという2つを一気に紹介しています。  
先程はお伝えしませんでしたが、NotebookLMは無料ユーザーは読み込めるソースの数の制限がなかなか厳しく、50個のソースしか読み込めないです。（50日分しか読み込めないということです）  
Google AI Proに加入することでソースの上限が50 → 300へと急拡大します。

Antigravityも無料で十分すぎるほどAIを使うことができます。  
が、Google AI Proに加入している場合は制限の上限が引き上げられます。  
要するに一つの課金で２つのサービスが使える、なのでAntigravityを推した。ということです。

ちなみにCursorの利用料金は月額で、Proで20$、Pro+で60$です。（大体3000~9500円）  
Google AI Proは月2900円なのでレートにもよりますが、現状だと最安です。  
なのでAI搭載のコードエディタをガッツリ使いつつ、NotebookLMもガッツリ使いつつ、という今回提案した形を採用する場合はAntigravityが最有力候補、ということになるのです。

ただ私の使い方はまだ初歩的で、YAMLの一括編集や、複数のコンテキストを理解させて1つのノートを構築させるといった程度ではあります。  
それでも、 複数のメモを横断してコンテキストを読み込み、一つのノートを構築できる 点は非常に強力です。

![画像](https://assets.st-note.com/img/1767417004-0mRQbNwkugfx9CSaJ4AoiMl5.png?width=1200)

Antigravityの画面

あとやる気があればの話になりますが、Obsidianのプラグインを作ることができます。  
というのもAntigravityやCursorは、会話形式でプログラミングができてしまう、通称バイブコーディングができるからです。私も一つ作ってみたものがあります。

![画像](https://assets.st-note.com/img/1767417078-N4tWhF7PRa6g1mpSxfdJcX2C.png?width=1200)

AntigravityでObsidianのプラグインを自作

コミュニティプラグインのSmartConnectionみたいなやつで、類似ノートをサイドバーに表示するというシンプルなプラグインです。  
こんな感じで自分に必要なものをピンポイントで作成してカスタマイズすることができるようになります。

![画像](https://assets.st-note.com/img/1767416715-APwK9eaDnZ8bqcsmOludTQ6h.png?width=1200)

Obsidian × Antigravityまとめ

  

### まとめ

Obsidianで日々の記録と知識の断片を一元管理し、GoogleのAIツール群（NotebookLMとAntigravity）でそれらを分析・活用するという、シンプルかつ強力な「セカンドブレイン」の構築方法を紹介しました。

ポイントは以下の3点です。

1. **Obsidian** ：Bases、Canvas、Thinoを活用して、日々のログやインプットを「シンプル」に集約・構造化する。
2. **NotebookLM** ：蓄積したMarkdownファイルを読み込ませ、自己分析や学習の振り返りにAIの分析力を活用する。
3. **Antigravity** ：執筆支援やデータ整理だけでなく、自分だけのプラグイン開発（バイブコーディング）までをコストパフォーマンス良く実現する。
![画像](https://assets.st-note.com/img/1767417130-ULWzhRvTBMNaqptrCsH6Gbck.png?width=1200)

今日のまとめ

「記録するだけ」で終わらせず、AIの力を借りて「活用する」ステージへ。  
ぜひ皆さんもこの構成を試してみてはいかがでしょうか。

最後に私の自己紹介も良ければご覧ください～  
それでは！

  

## いいなと思ったら応援しよう！

[![買うたび 抽選 ※条件・上限あり ＼note クリエイター感謝祭ポイントバックキャンペーン／最大全額もどってくる！ 12.1 月〜1.14 水 まで](https://assets.st-note.com/poc-image/manual/production/20271127_pointback_note_detail.jpg?width=620&dpr=2)](https://note.com/topic/campaign)

Obsidian × NotebookLM × Antigravity｜FURUYA