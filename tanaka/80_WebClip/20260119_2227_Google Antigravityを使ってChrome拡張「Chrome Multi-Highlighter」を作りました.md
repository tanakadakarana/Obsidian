---
title: "Google Antigravityを使ってChrome拡張「Chrome Multi-Highlighter」を作りました"
source: "https://zenn.dev/kobakichi/articles/chrome-multi-highlighter"
author:
  - "[[Zenn]]"
published: 2026-01-11
created: 2026-01-19
description:
tags:
  - "clippings"
image: "https://res.cloudinary.com/zenn/image/upload/s--LDTwJEdV--/c_fit%2Cg_north_west%2Cl_text:notosansjp-medium.otf_55:Google%2520Antigravity%25E3%2582%2592%25E4%25BD%25BF%25E3%2581%25A3%25E3%2581%25A6Chrome%25E6%258B%25A1%25E5%25BC%25B5%25E3%2580%258CChrome%2520Multi-Highlighter%25E3%2580%258D%25E3%2582%2592...%2Cw_1010%2Cx_90%2Cy_100/g_south_west%2Cl_text:notosansjp-medium.otf_37:kobakichi%2Cx_203%2Cy_121/g_south_west%2Ch_90%2Cl_fetch:aHR0cHM6Ly9zdG9yYWdlLmdvb2dsZWFwaXMuY29tL3plbm4tdXNlci11cGxvYWQvYXZhdGFyLzkzZDc0M2U5OGUuanBlZw==%2Cr_max%2Cw_90%2Cx_87%2Cy_95/v1627283836/default/og-base-w1200-v2.png?_a=BACAGSGT"
---
2026/01/11に公開

6

2[

![](https://storage.googleapis.com/zenn-user-upload/topics/b209aeee0d.png)

Chrome

](https://zenn.dev/topics/chrome)[

![](https://zenn.dev/images/topic.png)

extension

](https://zenn.dev/topics/extension)[

![](https://static.zenn.studio/images/drawing/idea-icon.svg)

idea

](https://zenn.dev/tech-or-idea)

## Google Antigravityを使ってChrome拡張「Chrome Multi-Highlighter」を作りました

某IT推進企業でAWSインフラエンジニアとして働いているkobakichiです。  
普段はTerraform、Ansibleを使ってインフラ構築、保守を担当しています。

前回の「Range Shot Annotator」に引き続き、Google Antigravityを使ってChrome拡張を作りました。  
今回の拡張機能も、開発から公開手順まで完全にAntigravityにお任せで作成しました。

Google Antigravityのリンクはこちらです。<iframe id="zenn-embedded__4c91dfc90bfe3" src="https://embed.zenn.studio/card#zenn-embedded__4c91dfc90bfe3" data-content="https%3A%2F%2Fantigravity.google%2Fpricing" frameborder="0" scrolling="no" loading="lazy" height="122"></iframe>

## 前提

すでに拡張機能としては同じ機能のものが複数あると思いますが、車輪の再発明大歓迎で作りました。

結果、自分で作ったもののほうが愛着湧く。うん。

## 拡張機能概要

Webページを調べものしていると「複数のキーワードを同時に探したい」と思うことってありませんか？

- 長い契約書PDFで「解約」「違約金」「更新」を一度に確認したい
- 技術ドキュメントで「エラー」「警告」「deprecated」を探したい
- 会議議事録で「TODO」「決定事項」「次回」をまとめてチェックしたい

ブラウザの標準検索（Cmd+F）では1つずつしか検索できず、複数キーワードを切り替えながら探すのは地味に面倒です。

そこで、**複数のキーワードを同時にハイライト表示し、色分けしてくれる** Chrome拡張機能を作りました。

## Chrome Multi-Highlighter

<iframe id="zenn-embedded__ee49a7fbc9e72" src="https://embed.zenn.studio/card#zenn-embedded__ee49a7fbc9e72" data-content="https%3A%2F%2Fchromewebstore.google.com%2Fdetail%2Fchrome-multi-highlighter%2Fnonbahheeamacolahbjdkdeeocellhij%3Fauthuser%3D0%26hl%3Dja" frameborder="0" scrolling="no" loading="lazy" height="122"></iframe>

完全無料でお使いいただけます。

## 何ができるのか？

この拡張機能では「複数のキーワードを同時にハイライト表示し、色分けして視覚的に探しやすくする」ことが可能です。  
シンプルに、複数キーワード検索→色分けハイライト→ナビゲーションという流れを実現することを目指しました。

### 1\. 起動はアイコンクリック一発

Chromeツールバーの拡張機能アイコンをクリックすると、画面右上にフローティングパネルが表示されます。  
パネルはドラッグで自由に移動できるので、邪魔にならない場所に配置できます。

### 2\. 複数キーワードを同時ハイライト

検索窓にスペースやカンマで区切ってキーワードを入力し、**Search**ボタンをクリック（または**Cmd+Enter**）するだけ。  
最大6色のハイライト色が自動で割り当てられ、どのキーワードがどこにあるか一目瞭然です。

### 3\. ナビゲーション機能

矢印ボタン（← →）でハイライト箇所を順番にジャンプできます。  
長いページでも目的の箇所にサクッと移動可能です。

### 4\. キーワード保存

入力したキーワードは自動保存されるので、次回同じページを開いた時もすぐに検索を再開できます。

## 操作方法

操作方法は以下の通りです。

| 操作 | アクション |
| --- | --- |
| **パネル表示** | 拡張機能アイコンをクリック |
| **キーワード入力** | スペースまたはカンマで区切って入力 |
| **ハイライト実行** | **Search** ボタン または `Cmd + Enter` |
| **次のマッチへ** | `→` ボタン |
| **前のマッチへ** | `←` ボタン |
| **ハイライト解除** | **Clear** ボタン |
| **パネル移動** | ヘッダー部分をドラッグ |
| **パネルを閉じる** | `Esc` キー または `×` ボタン |

## この拡張機能はどんな課題を解決するのか

- **複数キーワードの同時検索**: 標準の `Cmd+F` では1キーワードずつしか検索できませんが、この拡張機能なら複数キーワードを一度に検索できます。
- **視覚的な色分け**: キーワードごとに異なる色でハイライトされるため、どのキーワードがどこにあるか直感的に把握できます。
- **長文ドキュメントの効率的な確認**: ナビゲーション機能で、長いページでも目的のキーワードにサクッとジャンプできます。

## 使用技術

このツールは、軽量・高速であることを重視して作られています。

- **Chrome Extension (Manifest V3)**: 最新の仕様に準拠し、セキュリティとパフォーマンスを確保しています。
- **React + TypeScript**: 型安全性とコンポーネント設計により、保守性の高いコードを実現しています。
- **Vite**: 高速なビルドツールを採用し、開発効率を向上させています。
- **mark.js**: テキストハイライトのライブラリを使用し、高精度なマッチングを実現しています。
- **Shadow DOM**: ページのスタイルと干渉しないよう、Shadow DOM内にUIを描画しています。

## まとめ

「調べもの中に複数のキーワードを同時に探したい」。  
そんなシンプルなニーズに応える拡張機能です。

もし長いドキュメントを読む機会が多い方は、ぜひ一度試してみてください。

<iframe id="zenn-embedded__831548439ac24" src="https://embed.zenn.studio/card#zenn-embedded__831548439ac24" data-content="https%3A%2F%2Fchromewebstore.google.com%2Fdetail%2Fchrome-multi-highlighter%2Fnonbahheeamacolahbjdkdeeocellhij%3Fauthuser%3D0%26hl%3Dja" frameborder="0" scrolling="no" loading="lazy" height="122"></iframe>

[GitHubで編集を提案](https://github.com/kobakichi/kobakichi-zenn-contents/blob/main/articles/chrome-multi-highlighter.md)

6

2[![kobakichi](https://storage.googleapis.com/zenn-user-upload/avatar/93d743e98e.jpeg)](https://zenn.dev/kobakichi)

[kobakichi](https://zenn.dev/kobakichi)

栃木県民です。 東京の某IT推進企業でAWS インフラエンジニアとして働いています。 主に以下を専門にしています。 - AWS - Terraform - Ansible