---
title: "【Google Antigravity】新機能「Skills」について"
source: "https://zenn.dev/emp_tech_blog/articles/google-antigravity-skills"
author:
  - "[[Zenn]]"
published: 2026-01-22
created: 2026-01-24
description:
tags:
  - "clippings"
image: "https://res.cloudinary.com/zenn/image/upload/s--Krc6nCk3--/c_fit%2Cg_north_west%2Cl_text:notosansjp-medium.otf_55:%25E3%2580%2590Google%2520Antigravity%25E3%2580%2591%25E6%2596%25B0%25E6%25A9%259F%25E8%2583%25BD%25E3%2580%258CSkills%25E3%2580%258D%25E3%2581%25AB%25E3%2581%25A4%25E3%2581%2584%25E3%2581%25A6%2Cw_1010%2Cx_90%2Cy_100/g_south_west%2Cl_text:notosansjp-medium.otf_34:take6%2Cx_220%2Cy_108/bo_3px_solid_rgb:d6e3ed%2Cg_south_west%2Ch_90%2Cl_fetch:aHR0cHM6Ly9zdG9yYWdlLmdvb2dsZWFwaXMuY29tL3plbm4tdXNlci11cGxvYWQvYXZhdGFyL2FhYTMzODRhNGEuanBlZw==%2Cr_20%2Cw_90%2Cx_92%2Cy_102/co_rgb:6e7b85%2Cg_south_west%2Cl_text:notosansjp-medium.otf_30:EMP%2520Tech%2520Blog%2Cx_220%2Cy_160/bo_4px_solid_white%2Cg_south_west%2Ch_50%2Cl_fetch:aHR0cHM6Ly9zdG9yYWdlLmdvb2dsZWFwaXMuY29tL3plbm4tdXNlci11cGxvYWQvYXZhdGFyL2UxMmUyMDZmY2MuanBlZw==%2Cr_max%2Cw_50%2Cx_139%2Cy_84/v1627283836/default/og-base-w1200-v2.png?_a=BACAGSGT"
---
21

18[tech](https://zenn.dev/tech-or-idea)

## 🚀 はじめに

Google Antigravity、使っていますか？ 最近、新機能として **Skills** が追加されました。

これまでもカスタム指示（Customizations/Rules）でエージェントの挙動を調整できましたが、Skills はどうやら「もっと高度なタスク」を「必要な時だけ」実行させるための機能のようです。

「これは開発フローが変わるかもしれない...」と思い、実際に試してみました。 今回は、実用的な **自動コードレビュースキル** の作成を通して、その使い勝手を解説します。

![alt text](https://res.cloudinary.com/zenn/image/fetch/s--xuHo7qK8--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_1200/https://storage.googleapis.com/zenn-user-upload/deployed-images/e915121061ecf449037ad7b0.png%3Fsha%3D57e50018046f1f55701d0a22fc40735523bca3b7)

## 📚 概要: Skills（スキル）とは？

Skills は、エージェントに特定のタスクの進め方やベストプラクティスを教えるため **再利用可能なパッケージ** です。

単なるプロンプトテンプレートではありません。以下の 4 つの要素を組み合わせることで、複雑な作業を自律的に行わせることができます。

- **SKILL.md**: 指示書（いつ、どう動くか）
- **scripts/**: 道具（Python スクリプトなど、エージェントが実行するツール）
- **resources/**: 素材（チェックリスト、テンプレート、社内データ）
- **examples/**: お手本（理想的な出力例、コード規約）

これらをプロジェクトの `.agent/skills/` ディレクトリに置くだけで、エージェントは文脈に応じて勝手にスキルを使ってくれるようになります。

### なぜ Skills を使うのか？（3 つのメリット）

Customizations で長大な指示を書くのではなく、Skills として切り出すことには明確なメリットがあります。

#### 1\. コンテキストの節約と「集中力」の維持

Customizations にすべての業務マニュアルを詰め込むと、常に大量のトークンを消費するだけでなく、エージェントが指示の優先順位を見失う（ハルシネーションを起こす）原因になります。  
Skills は **必要な時だけ読み込まれる** （Dynamic Loading）ため、エージェントは目の前のタスクに集中でき、回答の精度が向上します。

#### 2\. 「確率」と「ロジック」のいいとこ取り

LLM は「滑らかな文章」を作るのは得意ですが、「文字数を正確に数える」「複雑な計算をする」といった厳密な処理は苦手です。  
Skills を使えば、 **厳密なチェックは `scripts/` （Python 等）に任せ、その結果を人間らしく伝える部分を LLM が担う** という、分業体制が構築できます。

#### 3\. Git でのバージョン管理と共有

Skills はフォルダとファイルの実体として存在するため、Git で管理できます。  
「新人メンバーが入ったら、とりあえずこの Skills フォルダを `git pull` しておいて」と言うだけで、チーム全員が同じ品質基準（Lint ルールやレビュー観点）を即座に共有できます。

## 🛠️ 準備

今回は準備編として、既存の React リポジトリをクローンし、そのコードに対してレビューを行っていく流れを想定します。

```bash
git clone https://github.com/facebook/react.git
```

今回は検証として、以下の挙動をする `code-reviewer` スキルを作ります。

1. コードを受け取ったら、まずスクリプトで機械的なミス（TODO 残存など）をチェックする。
2. チェックリストを参照し、セキュリティやパフォーマンスの観点漏れを防ぐ。
3. お手本に従って、優しく建設的なトーンで指摘する。

### フォルダ構成

プロジェクトルート（またはグローバル設定）に以下のディレクトリとファイルを作成します。Skills の面白い点は、フォルダ構成そのものがエージェントへの入力になる点です。

```
.
├── .agent/
│   └── skills/
│       └── code-reviewer/
│           ├── SKILL.md                  # メインの指示書
│           ├── scripts/
│           │   └── simple_linter.py      # 簡易チェックツール
│           ├── resources/
│           │   └── review_checklist.md   # レビュー観点リスト
│           └── examples/
│               └── review_style.md       # フィードバックの書き方見本
└── react/                                # レビュー対象のコード
```

それでは実際にファイルの中身を作っていきましょう。

### 1\. 指示書 (SKILL.md)

エージェントへの「指令」です。ここで各リソースを紐付けます。YAML フロントマターで名前と説明を定義します。

SKILL.md

```markdown
---
name: code-reviewer
description: コードの品質、安全性、可読性をチェックし、改善案を提示するスキル。PRレビューやリファクタリング相談時に使用。
---

# Code Reviewer Skill

提示されたコードに対してレビューを行い、改善点を指摘してください。

## レビュー手順

1. **自動チェックの実行**
   - 対象のコードファイルがある場合、以下のスクリプトを実行して基本的な問題をスキャンしてください。
   - コマンド: \`python scripts/simple_linter.py <ファイルパス>\`
   - コードがチャットに直接貼り付けられただけの場合は、このステップをスキップして目視確認してください。

2. **観点の確認**
   - \`resources/review_checklist.md\` を読み込み、各項目（セキュリティ、パフォーマンス等）についてコードを確認してください。

3. **フィードバックの作成**
   - \`examples/review_style.md\` のトーン＆マナー（口調・書き方）を参照してください。
   - 以下の構成で回答してください：
     1. **全体的な感想**: コードの意図を理解したポジティブなコメント。
     2. **重要課題**: バグやセキュリティリスクなど、必ず直すべき点。
     3. **改善提案**: 可読性向上や最適化のための提案（任意）。
     4. **修正コード例**: 具体的にどう直すべきかの Diff やコードブロック。

## 注意点

- 批判だけをせず、なぜ修正が必要なのか（Why）を説明してください。
- 変数名やコメントの不足についても積極的に指摘してください。
```

### 2\. 道具 (scripts/simple\_linter.py)

LLM だけでレビューすると見落としがちな単純な文字列マッチングは、従来のスクリプト（道具）に任せます。

simple\_linter.py

```python
import sys
import re

def analyze_code(file_path):
    """
    コード内の怪しいパターンを簡易検出するスクリプト
    """
    patterns = {
        "FIXME/TODO": r"(TODO|FIXME)",
        "Print Statement": r"(print\(|console\.log\()",
        "Hardcoded Token": r"(token|password|secret)\s*=",
        "Generic Exception": r"except Exception:",
    }

    print(f"--- Analyzing {file_path} ---")

    issues_found = False
    try:
        with open(file_path, 'r', encoding='utf-8') as f:
            lines = f.readlines()

        for i, line in enumerate(lines):
            for issue_name, pattern in patterns.items():
                if re.search(pattern, line):
                    # print文などは意図的な場合もあるのでWARNレベル
                    level = "WARN" if "Print" in issue_name else "review-required"
                    print(f"Line {i+1} [{level}]: found {issue_name} -> {line.strip()}")
                    issues_found = True

        if not issues_found:
            print("No obvious issues found by simple_linter.")

    except FileNotFoundError:
        print("Error: File not found.")

if __name__ == "__main__":
    if len(sys.argv) < 2:
        print("Usage: python simple_linter.py <file_path>")
    else:
        analyze_code(sys.argv[1])
```

### 3\. 素材 (resources/review\_checklist.md)

レビューの「質」を担保するためのカンニングペーパーです。ここに社内のセキュリティ基準などを書いておくと強力です。

review\_checklist.md

```markdown
# コードレビュー・チェックリスト

レビュー時は以下の観点を必ず確認してください。

## 🛡️ 安全性 (Security)

- SQL インジェクションや XSS の脆弱性はないか？
- パスワードや API キーがハードコーディングされていないか？
- 入力値の検証（バリデーション）は適切か？

## 🚀 パフォーマンス (Performance)

- ループの中で重い処理（DB 接続など）を行っていないか？
- 無駄なメモリアロケーションはないか？
- N+1 問題が発生する可能性はないか？

## 📖 可読性・保守性 (Readability)

- 変数名・関数名は「何をするか」を表しているか？（\`data\`, \`temp\` などの曖昧な名前は NG）
- 複雑なロジックにはコメントがついているか？
- 関数が長すぎないか（単一責任の原則）？
- エラーハンドリングは適切か（エラーを握りつぶしていないか）？

## 🧪 テスト (Testing)

- エッジケース（境界値、null、空リストなど）は考慮されているか？
```

### 4\. お手本 (examples/review\_style.md)

エージェントの「口調」や「指摘フォーマット」を制御します。これがあるだけで「AI っぽい回答」が「シニアエンジニアっぽい回答」に変わります。

review\_style.md

```markdown
# 良いレビューの書き方例

## 悪い例 ❌

> 10 行目の変数名がわかりにくいです。直してください。あとループが無駄です。

## 良い例 ✅

### 全体的な感想

機能の実装ありがとうございます！ロジックは明確でよく動いているようです。いくつか保守性とパフォーマンスの観点で提案があります。

### 改善提案

**1. 変数名の具体化 (Line 10)**
\`d\` という変数名だと、後から見た人が何のデータかわかりにくいです。格納されているのが日付データなら \`target_date\`、辞書なら \`user_profile\` などに変更することをお勧めします。

**2. ループ内での計算 (Line 15-20)**
ループの中で毎回 \`calculate_tax_rate()\` を呼んでいますが、税率は固定値のようなのでループの外に出すことでパフォーマンスが向上します。

\`\`\`python
# 修正案
tax_rate = calculate_tax_rate()  # ループ外へ移動
for item in items:
    price = item.price * tax_rate
    ...
\`\`\`

**3. エラーハンドリング**
\`except Exception:\` で全てのエラーをキャッチしていますが、予期せぬバグを見逃す可能性があります。\`ValueError\` など、想定されるエラーのみをキャッチするように変更しましょう。
```

## 💻 実践：エージェントにレビューさせてみた

ファイルを配置後、Reactリポジトリの一つ前のコミットのレビューを依頼してみました。  
こちらからは「スキルを使って」とは言わず、シンプルに一言だけ伝えます。

- **プロンプト**: 「1つ前の変更をコードレビューして」

### 1\. スキルの自動発動とスクリプト実行

エージェントは即座に意図を理解し、思考プロセス（Thought）の中で `code-reviewer` スキルを起動しました。

![alt text](https://res.cloudinary.com/zenn/image/fetch/s--ZBf6oh3R--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_1200/https://storage.googleapis.com/zenn-user-upload/deployed-images/6a3e7e541cb720beeac7dd38.png%3Fsha%3Dee5d292f438f3c7751a58150502a6ddfff4281a9)

### 2\. 生成されたレビュー結果

スクリプトの実行結果と、 `review_checklist.md` の観点を組み合わせ、 `review_style.md` に沿った回答が生成されました。

![alt text](https://res.cloudinary.com/zenn/image/fetch/s--9wqbPka9--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_1200/https://storage.googleapis.com/zenn-user-upload/deployed-images/8515dd5a4a3bde5cf529d856.png%3Fsha%3D2d77be0670b1d65d0b45b8a1e8b5e9ef8a294836)  
![alt text](https://res.cloudinary.com/zenn/image/fetch/s--kAF-Y8yF--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_1200/https://storage.googleapis.com/zenn-user-upload/deployed-images/b079568e93de32ddcd3c3895.png%3Fsha%3Dc80636e6ef2c14e6618e0a2673c88b2ab83b34ae)

## 💡 他に使えそうなアイデア

Code Reviewer 以外にも、工夫次第で様々なスキルが作れそうです。

#### 1\. テストコード生成 (test-generator)

- **Point**: `examples/` に「自社プロジェクトのテストの書き方（pytest の fixture の使い方など）」を置いておく。
- **効果**: 誰が書いても（AI に書かせても）同じ作法のテストコードが生成されるようになります。

#### 2\. SQL クエリ作成 (sql-expert)

- **Point**: `resources/` に `schema.md` （テーブル定義書） を置いておく。
- **効果**: 「先月の売上出して」と言うだけで、正しいテーブル結合を行った SQL が一発で出力されます。いちいちスキーマを教える必要がなくなります。

#### 3\. バグ報告書作成 (bug-reporter)

- **Point**: `resources/` にバグ報告の Markdown テンプレートを置く。 `scripts/` にログ収集スクリプトを置く。
- **効果**: エラーが起きた時に「報告書作って」と言うだけで、ログ付きの綺麗なチケット文章が完成します。

## 最後に

このアカウントでは、明日から開発フローを変えるための実践方法を共有していきます！  
更新を見逃さないよう、ぜひ今のうちに Zenn のアカウントをフォローしてお待ちください！！！

[GitHubで編集を提案](https://github.com/tkr-krhr-1/zenn-content/blob/main/articles/google-antigravity-skills.md)

21

18