---
title: "『まじん式 AI Slide Studio』の応用テクニック！｜まじん"
source: "https://note.com/majin_108/n/n5cb3cb5f3497"
author:
  - "[[まじん]]"
published: 2026-01-17
created: 2026-01-24
description: "こんにちは、まじんです。  まじん式プロンプト以降で一番のヒット作となった 「AI Slide Studio」について応用テクニックを5つご紹介いたします！  5つ目のみ、noteメンバーシップ限定での公開となります。  「AI Slide Studio」をまだ知らない方は以下の記事をご覧ください。  無料版（v1）  メンバーシップ版（v2）      【テクニック1】AI音声のトーンを変更  「AI Slide Studio」では、NotebookLMで生成したスライドPDFを ナレーション付き動画に変換できるんですが、  実はナレーション原稿に 括弧書きでトーンを指定してあげ"
tags:
  - "clippings"
image: "https://assets.st-note.com/production/uploads/images/244584994/rectangle_large_type_2_f458d33316bb8bb9d95e0e4c41834650.jpeg?fit=bounds&quality=85&width=1280"
---
![見出し画像](https://assets.st-note.com/production/uploads/images/244584994/rectangle_large_type_2_f458d33316bb8bb9d95e0e4c41834650.jpeg?width=1280)

## 『まじん式 AI Slide Studio』の応用テクニック！

[まじん](https://note.com/majin_108)

こんにちは、まじんです。

まじん式プロンプト以降で一番のヒット作となった  
「 **AI Slide Studio** 」について応用テクニックを5つご紹介いたします！

5つ目のみ、noteメンバーシップ限定での公開となります。

「 **AI Slide Studio** 」をまだ知らない方は以下の記事をご覧ください。

**無料版（v1）**

**メンバーシップ版（v2）**

  

![画像](https://assets.st-note.com/img/1768654705-XyDcmMN1RT3ux9L8bdkoF5Gn.png?width=1200)

---

## 【テクニック1】AI音声のトーンを変更

「AI Slide Studio」では、NotebookLMで生成したスライドPDFを  
ナレーション付き動画に変換できるんですが、

実はナレーション原稿に  
**括弧書きでトーンを指定してあげると、AI音声の口調が変わるんです！**

例えば、末尾に「 **（ささやき声で）** 」と付け足してあげると…

![画像](https://assets.st-note.com/img/1768647620-MiBhq6lvs98ajLzwEGXAeVxI.png?width=1200)

この通り、ささやきボイスに変わりました。面白いですよね。

他にも、ギャルっぽい口調で、と付け足してみると…

すごいですね。他にもアイデア次第で色々と楽しめそうです。

教育・医療・介護などの現場では、ゆったりとしたトーンに調整するとより伝わりそうですね。

ただし、 **括弧書きが字幕テロップにも記載されてしまうので、  
v2を使って読み上げ原稿の方に追記することをお勧めします。**

![画像](https://assets.st-note.com/img/1768648259-KBrt57nW8TLsu4JGkMVv96am.png?width=1200)

v2はこちら👇️（メンバーシップ限定）

---

## 【テクニック2】AI音声の "性別" を変更

デフォルトでは女性ボイスで固定になっていますが  
**Gemini（チャット欄）で「男性の声に変えてください」とリクエスト** すると…

**なんと、男性ボイスに変更することができます！**

同じ理屈で、Geminiに対して  
「 **すべてのナレーション音声を〇〇風にしてください。** 」などと、リクエストしてあげれば、無料版のv1でも動画全体の話し方のトーンを調整できますよ。

---

## 【テクニック3】トランジションを追加

「トランジション」は、カットとカット（シーンとシーン）の間に入れる「画面の切り替え効果」のことです。

Geminiに「 **シーンのつなぎ目にクロスディゾルブのトランジションを入れてください。** 」とリクエストすると

このように、よりハイクオリティな動画も作れようになります。  
Gemini 3は本当に賢いですね！  
他にもアイデア次第で色々とカスタムできそうです。

あまり無茶なリクエストをすると壊れてしまう可能性があるので、  
試しながらやってみてください。  
**なかなかバグが直らないときは最初からやり直すことをお勧めします。**

---

## 【テクニック4】ブループリントを更新

色々と改造してみて、今後もそのバージョンを使い続けたいなと思ったら、Gemの"知識"に追加しているテンプレートコード（ブループリント）を更新しましょう。  
  
① まず、改造後のCanvasのコードを全文コピー

![画像](https://assets.st-note.com/img/1768649522-GNqBU1hCj3PmRgfF0oOEwLV8.png?width=1200)

Ctrl + A → Ctrl + C で全文コピー

② メモ帳などに貼り付けて、上のドラッグした部分を削除し、  
以下の構文に書き換えて保存。

```javascript
const preloadedScripts = [
  "スライド1の原稿をここに生成",
  "スライド2の原稿をここに生成",
  "スライド3の原稿をここに生成"
];
```

![画像](https://assets.st-note.com/img/1768652339-9lLD4xUOHXBrFgvGtM8ce6iI.png?width=1200)

③ Gemの知識ファイルを②に差し替えればOK。

![画像](https://assets.st-note.com/img/1768649367-JAXevRNVUhEL0doQ8PO75a19.png?width=1200)

ファイル名は「react-app-template.txt」から変えないように！

このように、まじん式をベースに  
自分好みにアレンジして使っていただく形が理想的だと感じています。

最後にご紹介するテクニックが今回一番のおすすめです！  
こちらは **noteメンバーシップ限定** で公開いたします。

Google Workspace × Gemini 活用の研究コミュニティ 「Majincraft（…[このメンバーシップの詳細](https://note.com/majin_108/membership/join)

この記事が気に入ったらチップで応援してみませんか？

『まじん式 AI Slide Studio』の応用テクニック！｜まじん