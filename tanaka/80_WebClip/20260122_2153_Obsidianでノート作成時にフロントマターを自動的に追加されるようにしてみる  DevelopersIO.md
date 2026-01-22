---
title: "Obsidianでノート作成時にフロントマターを自動的に追加されるようにしてみる | DevelopersIO"
source: "https://dev.classmethod.jp/articles/obsidian-auto-frontmatter/"
author:
  - "[[西村祐二]]"
published: 2026-01-16
created: 2026-01-22
description:
tags:
  - "clippings"
image: "https://images.ctfassets.net/ct0aopd36mqt/271wVAxeN1rlKRsu2HX3i2/47104a220a7c282e824443292b7ac5bb/eyecatch_obsidian_1200x630.jpg"
---
どうも！オペ部の西村祐二です！

最近、Obsidianをちゃんと使っていこうと思って積極的に利用するようにしてます。  
Obsidianでノートを増やしていくと、毎回フロントマター（YAML）に「作成日」「更新日」「タグ」などを手で書くのが地味に面倒になります。

この記事では、 **新規ノート作成時点でフロントマターを自動的に追加する** やり方（Templater）をまとめます。

## 結論

やりたいことを分解すると、結論はこうなりました。

- 公式のコアプラグインのテンプレートは基本的に手動でテンプレートを挿入するためプラグインのため、今回の要件は満たさない。
- コミュニティプラグイン `Templater` の「新規作成時トリガー」＋「Folder templates」で新規作成時にフロントマターを自動挿入できる。

補足ですが、Obsidianのコア機能 `Templates` はテンプレート挿入自体はできますが、基本は **手動挿入** の仕組みです（コマンドで「Insert template」を実行する、またはアイコンからテンプレートを選択し追加する）。  
参考: [https://help.obsidian.md/Plugins/Templates](https://help.obsidian.md/Plugins/Templates)

## 前提条件

- Obsidianでコミュニティプラグインを使える状態にしておく（Community pluginsが利用可能）
- テンプレート用フォルダをVault内に用意しておく（例: `99_Templates/` や `Templates/` ）

## 手順

### 1\. テンプレート（雛形）を作る

Templaterのテンプレートは、YAML frontmatter の値に `<% ... %>` 形式で式を書けます。作成時刻を入れたいなら `tp.date.now()` で実現できます。

例（会議メモテンプレート）: サンプルでは `99_Templates/meeting_init.md` に下記のようなテンプレートにしています。

```markdown
---
created: <% tp.date.now("YYYY-MM-DD HH:mm") %>
categories:
 - work
tags:
  - meeting
---

## メモ
-
```

**ポイント**:

- **created**: `"YYYY-MM-DD HH:mm"` の部分を好みに合わせて変更OK

### 2\. Templaterの設定: 新規作成時にテンプレートを自動適用する

Templater側で「新規ノート作成時に走らせる」設定を有効にして、フォルダごとにテンプレートを割り当てます。

手順:

1. **Templaterをインストールして有効化**

![CleanShot 2026-01-16 at 14.47.06@2x](https://devio2024-media.developers.io/image/upload/v1768542699/2026/01/16/zmvnbfkx1ttprwkw9hnm.png)

1. Settings → Templater で次を設定
	- **Template folder location**: 例） `99_Templates`
	- **Trigger Templater on new file creation**: ON（新規作成時に実行）
	- **Enable folder templates**: ON（フォルダ別に割り当てる）

![CleanShot 2026-01-16 at 14.53.05@2x](https://devio2024-media.developers.io/image/upload/v1768542880/2026/01/16/cvtb4vxooinmlwex4hkl.png)

1. Folder templates に「00\_Inbox/meeting」→ `99_Templates/meeting_init.md` を割り当てる

![CleanShot 2026-01-16 at 14.56.02@2x](https://devio2024-media.developers.io/image/upload/v1768542998/2026/01/16/tkkv2bvdgtukpiqdsxkq.png)

参考（Templater設定）:

- [https://silentvoid13.github.io/Templater/settings.html](https://silentvoid13.github.io/Templater/settings.html)

参考:

- 「新規作成時にフロントマターを自動で入れたい」という相談と解決例（Obsidian Forum）: [https://forum.obsidian.md/t/insert-front-matter-template-automatically-at-file-creation-time/35351/2](https://forum.obsidian.md/t/insert-front-matter-template-automatically-at-file-creation-time/35351/2)
- `Templater` のFolder templatesが動かないときに確認すべき設定（Obsidian Forum）: [https://forum.obsidian.md/t/templater-folder-templates-not-working/75411](https://forum.obsidian.md/t/templater-folder-templates-not-working/75411)

### 動作確認

設定したフォルダで新規ノートを作成してみる

![CleanShot 2026-01-16 at 15.05.20@2x](https://devio2024-media.developers.io/image/upload/v1768543993/2026/01/16/bwl2mvzceqiuuxr65bhc.png)

想定どおりテンプレートを利用したページが作成されていることを確認

![CleanShot 2026-01-16 at 15.05.33@2x](https://devio2024-media.developers.io/image/upload/v1768544052/2026/01/16/piaflcj78pzdxgqw9ous.png)

## つまずきポイント

個人的にハマっところをメモしておきます。

### エラー: 新規作成したのにテンプレートが入らない

**原因**:

- `Trigger Templater on new file creation` がOFF
- `Template folder location` がテンプレを置いているフォルダと違う
- `Enabled folder templates` の割り当て先フォルダが違う（想定と別の場所にノートを作っている）

また、AIを使って整理しているとフォルダ構成が変わってしまって気づいたら動作してないことがありました。

## まとめ

- **新規作成時の自動挿入** は `Templater` を利用した（新規作成トリガー＋Folder templates）方法が手堅い
- **createdの日時挿入** はテンプレに `tp.date.now()` を書くだけでOK

`Templater` を使ってノート作成時にフロントマターを追加する方法をまとめてみました。  
高機能で他にもいろんな機能があるのでまた紹介したいと思います。

---

**参考リンク**:

- `Templates` （公式）: [https://help.obsidian.md/Plugins/Templates](https://help.obsidian.md/Plugins/Templates)
- `Templater` settings: [https://silentvoid13.github.io/Templater/settings.html](https://silentvoid13.github.io/Templater/settings.html)
- 新規作成時の自動挿入の相談例（Forum）: [https://forum.obsidian.md/t/insert-front-matter-template-automatically-at-file-creation-time/35351/2](https://forum.obsidian.md/t/insert-front-matter-template-automatically-at-file-creation-time/35351/2)
- Templaterの新規作成時トリガー関連（Forum）: [https://forum.obsidian.md/t/templater-folder-templates-not-working/75411](https://forum.obsidian.md/t/templater-folder-templates-not-working/75411)

この記事をシェアする

## 関連記事

 [![](https://images.ctfassets.net/ct0aopd36mqt/271wVAxeN1rlKRsu2HX3i2/47104a220a7c282e824443292b7ac5bb/eyecatch_obsidian_1200x630.jpg?w=1920&fm=webp) WindowsでOllamaを用いたLocal LLM環境をセットアップしてObsidianの拡張機能で生成AIによるタグ付けを行ってみた](https://dev.classmethod.jp/articles/obsidian-in-windows-set-tag-with-ai/)

2025.08.17