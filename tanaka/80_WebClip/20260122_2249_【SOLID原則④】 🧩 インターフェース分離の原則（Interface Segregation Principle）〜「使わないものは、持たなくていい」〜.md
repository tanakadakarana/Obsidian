---
title: "【SOLID原則④】 🧩 インターフェース分離の原則（Interface Segregation Principle）〜「使わないものは、持たなくていい」〜"
source: "https://qiita.com/toamoku-20220418/items/f78a305b28f20a186f1c"
author:
  - "[[toamoku-20220418]]"
published: 2026-01-19
created: 2026-01-22
description: "1. はじめに 🎯 この記事でわかること インターフェースって何のためにあるの？🤔 インターフェースを大きくしすぎると何が起きる？💥 インターフェース分離の原則（ISP）の考え方✨ 📌 そもそもインターフェースとは？ インターフェースは、 👉 「このクラ..."
tags:
  - "clippings"
image: "https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-user-contents.imgix.net%2Fhttps%253A%252F%252Fcdn.qiita.com%252Fassets%252Fpublic%252Farticle-ogp-background-afbab5eb44e0b055cce1258705637a91.png%3Fixlib%3Drb-4.0.0%26w%3D1200%26blend64%3DaHR0cHM6Ly9xaWl0YS11c2VyLXByb2ZpbGUtaW1hZ2VzLmltZ2l4Lm5ldC9odHRwcyUzQSUyRiUyRnFpaXRhLWltYWdlLXN0b3JlLnMzLmFwLW5vcnRoZWFzdC0xLmFtYXpvbmF3cy5jb20lMkYwJTJGMzY4MjU1NiUyRnByb2ZpbGUtaW1hZ2VzJTJGMTcxNjQ2NjMwMT9peGxpYj1yYi00LjAuMCZhcj0xJTNBMSZmaXQ9Y3JvcCZtYXNrPWVsbGlwc2UmYmc9RkZGRkZGJmZtPXBuZzMyJnM9N2Y3NjBlMzU2NmU4ODgzM2NiYzc5MjU5NzlmMDU0MDA%26blend-x%3D120%26blend-y%3D467%26blend-w%3D82%26blend-h%3D82%26blend-mode%3Dnormal%26s%3Dc6d439f1808b54839cd0b4dab6fd738e?ixlib=rb-4.0.0&w=1200&fm=jpg&mark64=aHR0cHM6Ly9xaWl0YS11c2VyLWNvbnRlbnRzLmltZ2l4Lm5ldC9-dGV4dD9peGxpYj1yYi00LjAuMCZ3PTk2MCZoPTMyNCZ0eHQ9JUUzJTgwJTkwU09MSUQlRTUlOEUlOUYlRTUlODklODclRTIlOTElQTMlRTMlODAlOTElMjAlRjAlOUYlQTclQTklMjAlRTMlODIlQTQlRTMlODMlQjMlRTMlODIlQkYlRTMlODMlQkMlRTMlODMlOTUlRTMlODIlQTclRTMlODMlQkMlRTMlODIlQjklRTUlODglODYlRTklOUIlQTIlRTMlODElQUUlRTUlOEUlOUYlRTUlODklODclRUYlQkMlODhJbnRlcmZhY2UlMjBTZWdyZWdhdGlvbiUyMFByaW5jaXBsZSVFRiVCQyU4OSVFMyU4MCU5QyVFMyU4MCU4QyVFNCVCRCVCRiVFMyU4MiU4RiVFMyU4MSVBQSVFMyU4MSU4NCVFMyU4MiU4MiVFMiU4MCVBNiZ0eHQtYWxpZ249bGVmdCUyQ3RvcCZ0eHQtY29sb3I9JTIzMUUyMTIxJnR4dC1mb250PUhpcmFnaW5vJTIwU2FucyUyMFc2JnR4dC1zaXplPTU2JnR4dC1wYWQ9MCZzPTJlMWZkMjViNjQ1NGQxZWRkZDY5NWMzY2Q4YjExZDFk&mark-x=120&mark-y=112&blend64=aHR0cHM6Ly9xaWl0YS11c2VyLWNvbnRlbnRzLmltZ2l4Lm5ldC9-dGV4dD9peGxpYj1yYi00LjAuMCZ3PTgzOCZoPTU4JnR4dD0lNDB0b2Ftb2t1LTIwMjIwNDE4JnR4dC1jb2xvcj0lMjMxRTIxMjEmdHh0LWZvbnQ9SGlyYWdpbm8lMjBTYW5zJTIwVzYmdHh0LXNpemU9MzYmdHh0LXBhZD0wJnM9MTU0NDlkOWM2Mzc1NzA3ODM0Nzc2MzZmMjkwM2UyMjQ&blend-x=242&blend-y=480&blend-w=838&blend-h=46&blend-fit=crop&blend-crop=left%2Cbottom&blend-mode=normal&s=ef5cae8eaee6a54f3107034a8461314b"
---
![](https://relay-dsp.ad-m.asia/dmp/sync/bizmatrix?pid=c3ed207b574cf11376&d=x18o8hduaj&uid=)

## Qiitaにログインして、便利な機能を使ってみませんか？

あなたにマッチした記事をお届けします

便利な情報をあとから読み返せます

[ログイン](https://qiita.com/login?callback_action=login_or_signup&redirect_to=%2Ftoamoku-20220418%2Fitems%2Ff78a305b28f20a186f1c&realm=qiita) [新規登録](https://qiita.com/signup?callback_action=login_or_signup&redirect_to=%2Ftoamoku-20220418%2Fitems%2Ff78a305b28f20a186f1c&realm=qiita)

## 1\. はじめに

**🎯 この記事でわかること**

- インターフェースって何のためにあるの？🤔
- インターフェースを大きくしすぎると何が起きる？💥
- インターフェース分離の原則（ISP）の考え方✨

**📌 そもそもインターフェースとは？**

インターフェースは、

> **👉 「このクラスは、これができますよ」という約束事**

を表すものです 📄✨

TypeScriptでは、  
**「どんなメソッドを持つか」** を決める設計図のような存在です。

## 2\. 失敗事例

まずは失敗例を見てみましょう。 👀

❌ よくある失敗：なんでも入れたインターフェース

```ts
// 悪い例：何でもできる巨大なインターフェース
interface Restaurant {
  makeHamburger(): void;
  makeRamen(): void;
  makeSushi(): void;
  makeCurry(): void;
  makeDessert(): void;
}
```

一見すると  
「全部まとまっていて便利そう！」  
に見えますよね 😊

でも、ここに落とし穴があります ⚠️

🤖 問題が起きるケース：ハンバーガーショップを作りたい

```ts
// ハンバーガーショップなのに全部実装しなきゃいけない...
class HamburgerShop implements Restaurant {
  makeHamburger(): void {
    console.log("🍔 美味しいハンバーガーを作ります！");
  }
  
  // 使わないのに実装が必要...😢
  makeRamen(): void {
    throw new Error("ラーメンは作れません");
  }
  
  makeSushi(): void {
    throw new Error("寿司は作れません");
  }
  
  makeCurry(): void {
    throw new Error("カレーは作れません");
  }
  
  makeDessert(): void {
    throw new Error("デザートは作れません");
  }
}
```

😢 何がつらいの？

- ハンバーガーショップは、ハンバーガーとデザートしか作れない
- それなのに メソッドを無理やり実装
- 不要なメソッドが増えて、意味がわかりにくくなる

👉 **「使わない機能に依存している状態」** です。

## 3\. 💡 インターフェース分離の原則（ISP）とは？

ここで登場するのが **インターフェース分離の原則(ISP)** です ✨

**📖 ISPの考え方**

> **クラスは、自分が使わないメソッドに依存してはいけない**

初心者向けに言い換えると👇

- 👉 「必要な機能だけを約束しよう」
- 👉 「1つのインターフェースに詰め込みすぎない」

**✅ 解決策：役割ごとに分ける**

インターフェースを **「できることごと」** に分割してみましょう ✂️✨

```ts
// 良い例：小さく分離されたインターフェース
interface BurgerMaker {
  makeHamburger(): void;
}

interface RamenMaker {
  makeRamen(): void;
}

interface SushiMaker {
  makeSushi(): void;
}

interface DessertMaker {
  makeDessert(): void;
}
```

👉 それぞれが とてもシンプルになりましたね 😊

**🧑 ハンバーガーショップクラスの場合**

```ts
// ハンバーガーショップは必要なインターフェースだけ実装
class HamburgerShop implements BurgerMaker, DessertMaker {
  makeHamburger(): void {
    console.log("🍔 美味しいハンバーガーを作ります！");
  }
  
  makeDessert(): void {
    console.log("🍰 デザートもご用意できます！");
  }
}
```

✔ 必要なインターフェースだけを実装  
✔ 無理な実装は一切なし

**🤖 ラーメン屋さんの場合**

```ts
// ラーメン屋さんはラーメンだけ
class RamenShop implements RamenMaker {
  makeRamen(): void {
    console.log("🍜 本格的なラーメンを作ります！");
  }
}
```

🎉 使わないメソッドは最初から持っていません！

🌟 何が良くなったの？

> ✅ 不要なメソッドを書かなくていい  
> ✅ クラスの役割がわかりやすい  
> ✅ 変更があっても影響が少ない  
> ✅ コードが自然で読みやすい

👉 これが インターフェース分離の原則（ISP） の効果です ✨

## 4\. 🧠 覚え方（初心者向け）

- 📌 「インターフェースは **小さく作る** 」
- 📌 「使わない約束は、 **しない** 」

この2つを覚えておけばOKです 👍

**🚀 実務でありがちな場面**

- 1つのinterfaceに項目が大量にある 😵
- implementsしたら空メソッドだらけ
- 「とりあえず共通化」でinterfaceが肥大化

👉 そんなときは  
**「このインターフェース、役割多すぎない？」**  
と考えてみましょう 👀✨

## 5\. ✨ まとめ

- ISPは ムダな **依存をなくす** ための原則
- インターフェースは **役割ごとに分ける**
- クラスは **必要な機能** だけを持つ
- TypeScriptのinterfaceは小さいほど使いやすい

## 6.　次回予告

次回はいよいよ 最終回：第5回 依存関係逆転の原則（DIP）🔄

SOLID原則の集大成として、  
**「依存関係をどう設計するか」** をやさしく解説していきます。

次回はこちら

- 第１回からご覧になるならこちら

## 7\. おわりに

インターフェース分離の原則（ISP）は、  
最初は少し地味に見えるかもしれません 🤔

でも実は、

- 「なんでこのクラス、こんなメソッド持ってるんだろう？」
- 「implementsしたら空のメソッドだらけ…😵」
- 「変更したら関係ないところが壊れた…💥」

といった 実務でよくあるつらさを防ぐための、とても大切な考え方です。

ISPを意識すると、  
**インターフェースは自然と 小さく・シンプルになり、**

- クラスの役割がはっきりする ✨
- コードが読みやすくなる 👀
- 将来の変更にも強くなる 💪

といった良いことがたくさん起こります。

はじめのうちは、

- 「とりあえず共通化」
- 「あとで使うかもしれないから入れておく」

とやりがちですが、そんなときこそ思い出してほしいのが **ISP** です 💡

- 👉 「この機能、本当に全員必要？」
- 👉 「インターフェース、役割多すぎない？」

この問いを持つだけで、設計の質はぐっと上がります。

最後まで読んでいただきありがとうございました！🎉

よろしければ他の記事もご覧頂けるとすごくうれしいです。

👍 いいね / 💬 コメントいただけると励みになります！

[0](https://qiita.com/toamoku-20220418/items/#comments)

コメント一覧へ移動

X（Twitter）でシェアする

Facebookでシェアする

はてなブックマークに追加する

新規登録して、もっと便利にQiitaを使ってみよう

1. あなたにマッチした記事をお届けします
2. 便利な情報をあとで効率的に読み返せます
3. ダークテーマを利用できます
[ログインすると使える機能について](https://help.qiita.com/ja/articles/qiita-login-user)

[新規登録](https://qiita.com/signup?callback_action=login_or_signup&redirect_to=%2Ftoamoku-20220418%2Fitems%2Ff78a305b28f20a186f1c&realm=qiita) [ログイン](https://qiita.com/login?callback_action=login_or_signup&redirect_to=%2Ftoamoku-20220418%2Fitems%2Ff78a305b28f20a186f1c&realm=qiita)

[1](https://qiita.com/toamoku-20220418/items/f78a305b28f20a186f1c/likers)

いいねしたユーザー一覧へ移動

3