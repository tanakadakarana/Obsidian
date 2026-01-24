---
title: "Geminiの「Gem」で自分専用のAWS認定講師を作ってみた | DevelopersIO"
source: "https://dev.classmethod.jp/articles/gemini-gem-aws-certification-instructor/"
author:
  - "[[鈴木純]]"
published: 2026-01-23
created: 2026-01-24
description:
tags:
  - "clippings"
image: "https://images.ctfassets.net/ct0aopd36mqt/wp-thumbnail-6a331d7c70f1897ca2ef1ad4cbe7c6bf/78c556633ae5115aa065636cc4a1160a/eyecatch_gemini"
---
## はじめに

みなさん、AWS 認定試験の勉強は捗っているでしょうか。 最近、「ソリューションアーキテクト – プロフェッショナル（SAP-C02）」の勉強をしていたのですが、せっかくなので AI を活用して効率的に学習できないかなと模索していました。

その結果、 Gemini の **Gem** を作成し、専用の「AWS 試験対策講師」を作ってみたところ、なかなか感触がよかったので共有します。

※Gem とは Gemini 上で独自にカスタマイズした AI アシスタントを作成できる機能です。

活用した結果かはわかりませんが、無事試験には合格できました。

## なぜGeminiなのか

「AI に PDF を読み込ませて学習をサポートしてもらう」という手法自体は、ChatGPT や Claude でも可能です。プロジェクトなどに前提となる試験ガイドなどを追加すれば似たようなことはできます。

しかし、今回は検討した上で Gemini を選びました。

理由としては「 [クイズ機能](https://support.google.com/gemini/answer/16275879?hl=ja&co=GENIE.Platform%3DDesktop&oco=0) 」が学習を進める上で便利だったからです。クイズ機能はこんな感じで Gemini が問題を作成してくれる機能です。

![スクリーンショット 2026-01-23 午前11.29.42.png](https://devio2024-2-media.developers.io/upload/suzuki-jun/2026-01-23/aA63Xfi7bpAH.png)

選択肢を選ぶと正解・不正解が表示されます。  
![スクリーンショット 2026-01-23 午前11.35.53.png](https://devio2024-2-media.developers.io/upload/suzuki-jun/2026-01-23/uq93EfJiJ0Yp.png)

不正解の場合はなぜ不正解なのかの解説もしてくれます。  
![スクリーンショット 2026-01-23 午前11.52.18.png](https://devio2024-2-media.developers.io/upload/suzuki-jun/2026-01-23/1LZPsPeQrzbW.png)

作成したクイズは共有もできます。イメージを知りたい方は触ってみてください。

また、わからない内容や AWS サービスについてそのチャット内ですぐに解説してもらうこともできます。

例えば、問題の中で `StringNotLike` が分からず間違ったとしましょう。  
すぐ「SCP で設定できる StringNotLike について解説して」とチャット内にコメントしてみます。

すると、その解説をぱっとまとめてくれます。  
![スクリーンショット 2026-01-23 午前11.38.01.png](https://devio2024-2-media.developers.io/upload/suzuki-jun/2026-01-23/YGruwr5opoIJ.png)

この「 **問題を解く → その場で解説** 」というサイクルをすぐに回せるのが良さそうだなと思い、クイズ機能がある Gemini を使ってみました。

## Gemを作成する

それでは、実際に作成した手順を紹介します。

### 事前準備

Gem を作成する前に、前提知識としてインプットしたい資料を集めておきましょう。今回はソリューションアーキテクト – プロフェッショナル（SAP-C02）用として以下の試験ガイドをダウンロードしました。

[AWS Certified Solutions Architect - Professional (SAP-C02) 試験ガイド](https://d1.awsstatic.com/ja_JP/training-and-certification/docs-sa-pro/AWS-Certified-Solutions-Architect-Professional_Exam-Guide.pdf)

他には Well-Architected の６つの柱の PDF も合わせて用意しました。この辺は試験に合わせて適宜変更してください。

- [持続可能性の柱](https://docs.aws.amazon.com/ja_jp/wellarchitected/latest/sustainability-pillar/wellarchitected-sustainability-pillar.pdf#sustainability-pillar)
- [コスト最適化の柱](https://docs.aws.amazon.com/ja_jp/wellarchitected/latest/cost-optimization-pillar/wellarchitected-cost-optimization-pillar.pdf#welcome)
- [パフォーマンス効率の柱](https://docs.aws.amazon.com/ja_jp/wellarchitected/latest/performance-efficiency-pillar/wellarchitected-performance-efficiency-pillar.pdf#welcome)
- [信頼性の柱](https://docs.aws.amazon.com/ja_jp/wellarchitected/latest/reliability-pillar/wellarchitected-reliability-pillar.pdf#welcome)
- [セキュリティの柱](https://docs.aws.amazon.com/ja_jp/wellarchitected/latest/security-pillar/wellarchitected-security-pillar.pdf#welcome)
- [運用上の優秀性の柱](https://docs.aws.amazon.com/ja_jp/wellarchitected/latest/operational-excellence-pillar/wellarchitected-operational-excellence-pillar.pdf#welcome)

１つの PDF が大きすぎると一気に読み込んでコンテキストをオーバーしてしまうので、Well-Architected の PDF は６つ個別に用意しましょう。

### 1\. Gem の作成

Gemini の画面左側にある「Gem」をクリックし、新しい Gem を作ります。  
![スクリーンショット 2026-01-23 午前11.17.33.png](https://devio2024-2-media.developers.io/upload/suzuki-jun/2026-01-23/P1grWlTAFMJx.png)

### 2\. 基本情報とカスタム指示の設定

名前や説明など以下のように設定しました。名前や説明などは好きに設定してみてください。

- 名前：SAP-C02 講師
- 説明：AWS 認定ソリューションアーキテクト – プロフェッショナル（SAP-C02）の合格を支援するエキスパート
- カスタム指示:

```
役割:
あなたはAWS認定ソリューションアーキテクト – プロフェッショナル（SAP-C02）の合格を支援するエキスパート講師です。知識に添付された試験ガイドとAWS Well-Architectedのベストプラクティスに沿って回答してください。

目的:
ユーザーが試験に合格できるよう、ケーススタディ形式の練習問題を提供し、深い技術的洞察に基づいた解説を行います。問題は本番と同等の難易度を意識してください。

トーン: 励ましつつも、プロフェッショナルとして厳格で正確なアドバイスを行ってください。
```

- デフォルトツール： **Canvas**
- 知識：事前準備で用意した PDF

**特にデフォルトツールを `Canvas` にするのを忘れないようにしましょう。**  
Canvas は別ウィンドウでドキュメントやクイズを展開する機能です。

カスタム指示は試験に合わせて適宜調整してください。

最終的にはこんな形になりました。  
![スクリーンショット 2026-01-23 午前11.25.28.png](https://devio2024-2-media.developers.io/upload/suzuki-jun/2026-01-23/DOQ7PrEdwyMM.png)

## 試してみる

Gem の作成が完了したら、試しに問題を出してもらいましょう。

「ネットワークの問題を５問出題して」とコメントしたところ、数十秒程度で問題が作成されました。

![スクリーンショット 2026-01-23 午前11.51.03.png](https://devio2024-2-media.developers.io/upload/suzuki-jun/2026-01-23/zqhjDbNPBRza.png)

最後まで進めると、完了画面が表示されます。正答数などをまとめて確認できますね。  
![スクリーンショット 2026-01-23 午前11.54.36.png](https://devio2024-2-media.developers.io/upload/suzuki-jun/2026-01-23/S3AnDxe1dXeX.png)

特に便利なのが `More questions` です。追加で問題数を増やしたり、問題の難易度を変更できます。  
![スクリーンショット 2026-01-23 午前11.55.28.png](https://devio2024-2-media.developers.io/upload/suzuki-jun/2026-01-23/VpoMjbQUAJZW.png)

試験に合わせて難易度を調整したり、苦手分野を中心に解いたりできます。

ここまで準備ができたら問題をたくさん解くなり、細かい解説をしてもらって学習を進めていきましょう。

## 注意点

この Gem に限ったことではありませんが、生成 AI を使う上ではある程度注意しておくべきことを明記しておきます。

### 必ず試験に沿った問題が出るわけではない

試験ガイドに沿っているだけなので、実際の問題と同じ問題が出るわけではありません。試験勉強のサポートとして活用しましょう。

### 問題の傾向が偏ることがある

明確に出して欲しい問題を指示しないと、同じような問題が出ることもあります。試験ガイドを読んで、 **重点的に出して欲しいサービスなどを指示すると効果的です。**

### 試験で問われる内容とGeminiの回答に乖離がある可能性がある

AWS のアップデートの関係で、Gemini の回答と試験問題の回答が変わる可能性もあります。それを認識した上で利用しましょう。

## まとめ

Gemini のクイズ機能を使った試験対策 Gem を作成してみました。今回は AWS SAP 用でしたが、与える情報を変えれば他の試験に応用できます。

必ず回答が正しいかは判断する必要がありますが、苦手分野の洗い出しなどに活用してみてください。

この記事をシェアする