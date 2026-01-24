---
title: "Skills が増えすぎて管理に困ったら Obsidian で一覧化しよう｜松濤Vimmer"
source: "https://note.com/shotovim/n/n714c8519499d"
author:
  - "[[松濤Vimmer]]"
published: 2026-01-17
created: 2026-01-24
description: "先日投稿したポストの評判が良かったので今回は具体的にどのようにSkillsを管理するかについて解説します。   Skills が多くなり管理に困っていたんですが、Obsidian の Bases を使ったらきれいに整理できました。  やりかたは Skills のフォルダを Obsidian の Vault 配下にシンボリックリンクして Bases でフィルタリングするだけ。  Bases の作成は Obsidian Skills からできるので Bases… pic.twitter.com/a2pvCkZnuO — 松濤Vimmer (@shotovim) January 16, 20"
tags:
  - "clippings"
image: "https://assets.st-note.com/production/uploads/images/244457431/rectangle_large_type_2_7848c098f57f31b46f9d9ba25546efb6.png?fit=bounds&quality=85&width=1280"
---
![見出し画像](https://assets.st-note.com/production/uploads/images/244457431/rectangle_large_type_2_7848c098f57f31b46f9d9ba25546efb6.png?width=1280)

## Skills が増えすぎて管理に困ったら Obsidian で一覧化しよう

[松濤Vimmer](https://note.com/shotovim)

先日投稿したポストの評判が良かったので今回は具体的にどのようにSkillsを管理するかについて解説します。

## Skills が増えると何が困るのか

Skills を増やしすぎると、「どの Skills が使えるんだっけ？」という状態になりがちです。便利だなと思ってマーケットプレイスからダウンロードしたり、欲しい機能があれば自分で作ったりしているうちに、気づけば Skills がどんどん増えてしまいます。

もちろん /skills コマンドを使えば一覧で確認できますが、数が多くなると見にくくなり、結果として使わなくなってしまうこともあります。。

![画像](https://assets.st-note.com/img/1768617668-McFjw2XRH8nyimNZsW4VGTlO.png?width=1200)

わたしは普段から Obsidian を使っているので、これとうまく組み合わせられないかと考えました。そこで思いついたのが Obsidian の Bases を使った方法です。

## Obsidian の Bases とは

Obsidian の Bases はデータベース機能のようなものです。他のノートアプリのデータベースと違い、フィルタリングでデータベースを作成するという作りになっています。そのため、数あるファイルの中から特定のファイルのみをデータベース化できます。今回だと Skills のファイルだけを抽出するといったことができます。

詳細はこちらをご覧ください。

### Bases作成が簡単に

Obsidian の Bases は使いやすく直感的ですが、特定のプロパティをカスタマイズするなど高度な機能もあります。今まではある程度の知識がないとこちらの機能を活用できませんでしたが、Obsidian Skills が登場したことで解決しました。Obsidian Skills には Bases を作る機能があり、これを使うことで複雑なプロパティの作成やフィルタリングが簡単にできるようになります。

Obsidian Skills のダウンロード方法などは割愛しますが、リポジトリにインストール方法が載っているので、そちらを参照してください。

## Skills を Vaultで管理しよう

### Skills を Vault に持ってくる

SkillsをObsidianのbasesで管理するためにはObsidianのValut配下にSkillsファイルを置く必要があります。

通常、Skills はホームディレクトリの.claude 配下やプロジェクト配下にあることが多いので、Vault 上にはありません。そのため、Obsidian で管理ができないという問題があります。

そこで使うのが **シンボリックリンク** です。シンボリックリンクは実体は別の場所にありつつ、あたかもそこに存在するかのように参照できる仕組みです。これを使うことで実体は.claude フォルダにあるまま、Vault 配下からも Skills フォルダを参照できるようになります。これによって Obsidian 側が Skills ファイルを認識してくれるので、Bases を使ったフィルタリングが可能になります。

### コマンド例

```ruby
# Vault内にskillsフォルダへのシンボリックリンクを作成
ln -s ~/.claude/skills ~/your-vault-path/skills
```

```javascript
ln -s ~/.claude/plugins/marketplaces ~/your-vault-path/plugins/marketplaces
```

↓実際の例

![画像](https://assets.st-note.com/img/1768618462-Z0x8nhQIKFaEvVM2e5DcdfHu.png?width=1200)

実行するとVault配下にSkills関連のフォルダが配置されていることがわかります。

![画像](https://assets.st-note.com/img/1768620803-2NcSwD9xfbK3UEOiBs0I6ehp.png)

## Bases の作成

あとは Obsidian Skills を呼んで「このような Bases を作ってください」と指示すれば、Bases を作成でき、Skills を一覧化できます。以下にわたしが指示した具体例を載せます。

![画像](https://assets.st-note.com/img/1768619386-jyNfG6lCinpQwMmRtDUEuZHd.png?width=1200)

![画像](https://assets.st-note.com/img/1768619410-Svxk3aIwD4pFyjt2UCcBAlVY.png?width=1200)

> ↑AskUserQuestionを使うと要件がまとまるのでおすすめです。

## 作成したBases

以下が今回作成したBasesになります。

![画像](https://assets.st-note.com/img/1768620452-wtDV9gXBlCKej0ZHsoyurNpc.png?width=1200)

テーブルビュー

![画像](https://assets.st-note.com/img/1768620452-7gJQ8fAjmb4WLZTOU3ekr1o5.png?width=1200)

カードビュー

## まとめ

今回は Skills に限った話でしたが、シンボリックリンクとうまく組み合わせることで、Obsidian 上でエージェント周りの管理を便利に行うことができます。ぜひお試しください。

## いいなと思ったら応援しよう！

Skills が増えすぎて管理に困ったら Obsidian で一覧化しよう｜松濤Vimmer