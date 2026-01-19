---
title: "Google Antigravityとは？使い方や料金をご紹介"
source: "https://aismiley.co.jp/ai_news/google-antigravity-how-to/"
author:
  - "[[AIsmiley]]"
published: 2026-01-09
created: 2026-01-19
description: "開発向けのAIエージェントは次々とリリースされるけれど、もっと自律的に作業を進められるようになってほしいと感じている人はいませんか？この記事では、そんな人にぜひ使ってほしいGoogle Antigravityについて詳しくご紹介します。"
tags:
  - "clippings"
image: "https://aismiley.co.jp/wp-content/uploads/2026/01/GoogleAntigravity.jpg"
---
最終更新日:2026/01/09

![](https://aismiley.co.jp/wp-content/uploads/2026/01/GoogleAntigravity-1024x576.jpg) Google Antigravityとは？

開発向けのAIエージェントは次々とリリースされていますが、もっと自律的にタスクを進められる存在になってほしいと感じている人も多いのではないでしょうか。

人手不足とAIの進化により、今開発の現場はタスクの進め方そのものを見直す時期にきていると言えるでしょう。このような背景から、人間と協働できるAIエージェントへのニーズは今後さらに高まっていくと考えられます。

この記事では、開発の現場で新しいAIとの協働環境を構築できるGoogle Antigravityについて詳しくご紹介します。

目次 \[[hide](https://aismiley.co.jp/ai_news/google-antigravity-how-to/#)\] \[[show](https://aismiley.co.jp/ai_news/google-antigravity-how-to/#)\]

## Google Antigravityとは？

![](https://aismiley.co.jp/wp-content/uploads/2026/01/GoogleAntigravity2.jpg)

Google AntigravityとはGoogleが2025年11月19日に発表した、AIエージェントを中核に据え、開発全体を統括できる新しい開発プラットフォームです。

Google Antigravityは、「AIエージェントは単なるサイドバー上のチャットボットではなく、作業に専念できる専用スペースを持った方がよい」という考え方のもとに設計されています。

そのためGoogle Antigravityには次の2つの異なる操作画面があります。

| **画面の種類** | **概要** |
| --- | --- |
| エディタービュー（Editor View） | 手動で作業したい時用にある、同期的な開発ワークフローをそのまま活かせる設計の操作画面 |
| マネージャーサーフェス（Manager Surface） | 複数のAIエージェントを生成・管理し、それぞれが非同期に異なる作業空間で動作する様子をまとめて把握・制御できる専用の操作画面 |

作業指示を出す部屋（Manager）」と「実際に作業する部屋（Editor）」が分かれているので、AIに作業を任せている間に、自分は別のことができます。

## Google Antigravityでできること

![](https://aismiley.co.jp/wp-content/uploads/2026/01/GoogleAntigravity1.png)

Google Antigravityでできることを、「エージェント機能」「エディター機能」「ブラウザ機能」の3つにわけてご紹介します。

### エージェント機能

エージェント機能はGoogle Antigravityの中核となるAI機能で、最先端の大規模言語モデルを基盤とした「AIが自分で考えて動く機能（マルチステップ推論システム）」が搭載されています。

この「AIが自分で考えて動く機能（マルチステップ推論システム）」とは最新世代の推論モデルを「頭脳」にして、1回で答えず、考えを重ねながら仕事を進める仕組みです。

エージェント機能は主に以下の要素をまとめた仕組み全体で成り立っています。

| **項目** | **役割** |
| --- | --- |
| 推論モデル | エージェントの頭脳 |
| ツール | エディタやブラウザなどで情報取得や操作を可能にする |
| アーティファクト | エージェントが生成するコードやドキュメントなどの成果物 |
| 知識 | 回答の前提となる知識 |

そのため、推論モデルがそれぞれの要素を統括して仕事を進めていると考えるとわかりやすいでしょう。

それぞれの要素が果たす役割を、もう少し詳しく解説します。

参考：[Google Antigravity Documentation「Agent」](https://antigravity.google/docs/agent)

#### 推論モデル

![](https://aismiley.co.jp/wp-content/uploads/2025/12/google-antigravity1.png)

画像出典：[Google Antigravity Documentation「モデル」](https://antigravity.google/docs/models)

Google Antigravityのエージェント機能において、頭脳として活用できる主なモデルは次の通りです。

| **推論モデルの種類** | **特徴と開発において選ぶメリット** |
| --- | --- |
| Gemini 3 Pro (high) | 複雑な要件整理や大規模コードベースの理解など、精度最優先の開発タスクに向いている |
| Claude Sonnet 4.5 | 自然言語の理解力が高く、仕様書作成や設計意図の言語化に強みがある |
| GPT-OSS | オープンなモデル特性を活かし、柔軟なカスタマイズや検証用途に向いている |

会話入力欄の下にあるモデルセレクターのドロップダウンから、タスクの内容や求める精度に応じて推論モデルを選んで使い分けることで、作業の効率化とコスト削減を図れます。

参考：[Google Antigravity Documentation「モデル」](https://antigravity.google/docs/models)

#### アーティファクト（AIが作成した成果物）

エージェント機能においては、エージェントが作業を進めるため、または人間に思考や進捗を伝えるために生成するものを「アーティファクト（AIが作成した成果物）」と呼んでいます。

ユーザーは、成果物に対してフィードバックを行うことで、エージェントの進行方向を適切に調整できます。

参考：[Google Antigravity Documentation「Artifacts」](https://antigravity.google/docs/artifacts)

#### 知識

ナレッジアイテム(Knowledge Item)とは、特定のトピックに関する関連情報をまとめた情報の集合体です。

すべてのナレッジアイテムの要約情報はエージェントが常に参照可能な状態になっています。

エージェントが会話に関連するナレッジアイテムを見つけると、ナレッジアイテム内の成果物を自動的に読み込み、該当する情報を回答や作業に活用します。

参考：[Google Antigravity Documentation「Knowledge」](https://antigravity.google/docs/knowledge)

#### エージェントのモード・設定

エージェント機能では、モード設定と全体設定を行えます。

モードとはエージェントの会話スタイルを決める設定です。

| **モードの種類** | **概要** |
| --- | --- |
| 計画モード(Planning) | - エージェントがタスクを実行する前に計画を立てるモード - 深いリサーチが必要な場合、複雑なタスク、共同作業に適している |
| 高速コード(Fast) | - エージェントが計画を立てず直接タスクを実行するモード - 変数名の変更、いくつかのbashコマンドの実行など短時間で完了するシンプルな作業に適している |

全体設定とはすべてのエージェントとの会話に共通する設定で、設定画面の「Agent」タブから確認・変更できます。

主な全体設定の内容は次の通りです。

| **項目** | **概要** |
| --- | --- |
| 成果物レビュー方針（Artifact Review Policy） | - 成果物のレビューに関する挙動を「Always Proceed」と「Request Review」の2つから選んで設定 - 「Always Proceed」とはエージェントがレビューを求めず、そのまま処理を続行する設定 - 「Request Review」とはエージェントが常にユーザーにレビューを要求する設定 |
| ターミナルコマンド自動実行（Terminal Command Auto Execution） | - ターミナルコマンド生成ツールに関する設定を「Request Review」と「Always Proceed」の2つから選んで設定 - 「Request Review」とはターミナルコマンドを自動実行できなくする設定（設定可能なAllowリストに含まれるものを除く） - 「Always Proceed」とはエージェントがレビューを求めずに実行する設定(設定可能なDenyリストに含まれるものを除く) |
| ワークスペース外ファイルへのアクセス（Agent Non-Workspace File Access） | - 現在のワークスペース外にあるファイルの閲覧・編集をエージェントに許可する設定 |

行いたいタスクに合わせてモードや設定を変更することで、より開発作業を効率化できます。

参考：[Google Antigravity Documentation「エージェントモード/設定」](https://antigravity.google/docs/agent-modes-settings)

#### MCP（Model Context Protocol）

Google AntigravityはMCPに対応しています。

MCPとは、エディタがローカルツールやデータベース、外部サービスと安全に接続するための標準プロトコルです。

MCPを用いた連携をすることにより、Google Antigravityではエディタで開いているファイルだけでなく、リアルタイムの外部コンテキストを利用できるようになります。

MCPの接続手順は以下の通りです。

1. エディタのサイドパネル上部にある「…」からMCP Storeを開く
2. 対応サーバー一覧から選び、「Install」をクリック
3. 画面の指示に従ってアカウントを安全に連携（必要な場合）

MCPを利用することでGoogle Antigravityにおいて安全に、より充実したエージェント機能を使うことができるでしょう。

参考：[Google Antigravity Documentation「Antigravity Editor:MCP統合」](https://antigravity.google/docs/mcp)

#### ルール・ワークフロー

エージェント機能では、ルールとワークフローを設定できます。

ルールとはエージェントが従う制約や行動指針をユーザーが手動で定義する仕組みで、ローカルレベル（ワークスペース単位）とグローバルレベル（全体共通）の両方で設定可能です。

ルールの作成手順は次の通りです。

1. エディタのエージェントパネル上部にある「…」から Customizations を開く
2. Rules パネルに移動
3. 「+ Global」で全体共通ルールを作成、または「+ Workspace」で特定ワークスペース用ルールを作成

ワークフローとは、繰り返し行う作業を一連の手順として定義できる仕組みで、定型作業の自動化に向いています。

ワークフローの作成手順は以下の通りです。

1. エージェントパネルの「…」から Customizations を開く
2. Workflows パネルへ移動
3. 「+ Global」または「+ Workspace」で新規作成

モードや設定と同じく行いたいタスクに応じて作成しておくことで、より作業が効率化できるでしょう。

参考：[Google Antigravity Documentation「ルール/ワークフロー」](https://antigravity.google/docs/rules-workflows)

### エディター機能

Google Antigravityの主な操作入口となるのがエディター機能で、VS Codeのコードベースをもとに構築されています。

エージェントと協働しながら開発を進めることも可能で、拡張機能も追加できるため、自分の開発スタイルに合わせてGoogle Antigravityをカスタマイズできます。

参考：[Google Antigravity Documentation「Editor」](https://antigravity.google/docs/editor)

### ブラウザ機能

ブラウザ機能とは、Google Antigravityからサブエージェントを通じてChromeブラウザを開き操作できる機能です。

操作内容は記録され、スクリーンショットや動画として成果物（Artifacts）にまとめられます。

使用しない場合は、設定画面の「Browser」セクションからすべてのブラウザツールを無効化することもできます。

参考：[Google Antigravity Documentation「Browser」](https://antigravity.google/docs/browser)

参考：[Google Antigravity Documentation「Google Antigravity」](https://antigravity.google/docs/home)

## Google Antigravityの始め方

Google Antigravityをダウンロードする前に、まずは自分のPCのOSが以下の推奨環境になっているかを確認しましょう。

| 項目 | 概要 |
| --- | --- |
| macOS | - Appleのセキュリティアップデート対象のmacOSバージョン（通常は最新バージョンとその直前の2世代） - 最低対応バージョンは macOS 12（Monterey）  ※Intel（x86）非対応 |
| Windows | - Windows 10（64bit） |
| Linux | - glibc 2.28以上、glibcxx 3.4.25以上 |

環境が確認できたら[公式ページ](https://antigravity.google/download?_gl=1*fg3h4t*_up*MQ..*_ga*MzU5OTM5NDgxLjE3NjY1NDAwODQ.*_ga_47V54ZJ3EV*czE3NjY1NDAwODMkbzEkZzAkdDE3NjY1NDAwODMkajYwJGwwJGgw)よりダウンロードを行ってください。

参考：[Google Antigravity Documentation「はじめに」](https://antigravity.google/docs/get-started)

## Google Antigravityの使用にかかる料金

![](https://aismiley.co.jp/wp-content/uploads/2026/01/GoogleAntigravity3.jpg)

Google Antigravityは2025年12月現在パブリックプレビューとして個人開発者向けに無料で公開されています。

今後正式リリースされた際には料金が発生する可能性もあることから、公式のアナウンスを確認するようにしましょう。

参考：[Google for Developers「Google Antigravityとビルドを始めましょう。これは私たちの新しいエージェント開発プラットフォームです」](https://developers.googleblog.com/build-with-google-antigravity-our-new-agentic-development-platform/)

## Google Antigravityで開発をする際の注意点

2025年12月現在、Google Antigravityの公式ホームページには「Google Antigravity 追加利用規約」が掲載されています。

これはGoogle Antigravityで開発をする際の注意点についてまとめられたもので、主に以下のことが記載してあります。

- Google Antigravityをダウンロード・インストール・利用した時点で利用規約やプライバシーポリシーに同意したものとみなされる
- Google Antigravityを利用すると、操作データやフィードバック内容が記録・保存される
- Google AntigravityのAIエージェントは、自律的または半自律的にタスクを実行できるが責任はすべてユーザー側にある
- 収集されたやり取りのデータはGoogleとAlphabetの研究、プロダクト改善、機械学習技術の向上に利用される
- 第三者またはOSSモデルを使用する場合は、そのモデル独自の利用規約が適用される

業務利用では特に、利用規約やプライバシーポリシーにあらかじめ目を通し、内容や責任の所在について理解しておきましょう。

## まとめ

Google AntigravityとはGoogleが2025年11月19日に発表した、AIエージェントを中核に据え、開発全体を統括できる新しい開発プラットフォームです。

この記事も参考にして、ぜひAIと適切に協働しながら開発を進めてみてください。

アイスマイリーでは、生成AI のサービス比較と企業一覧を無料配布しています。課題や目的に応じたサービスを比較検討できますので、ぜひこの機会にお問い合わせください。