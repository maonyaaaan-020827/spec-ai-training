# Day 5 — 4/7 (火): リサーチ実務 + ハルシネーション対策

## 今日のゴール

AI出力の信頼性を検証する方法（ファクトチェック）を習得し、ソース引用付きのリサーチレポートを作成する。

---

## 必須課題

### 課題1: Deep Research で業界リサーチを実施する

**Day3 とは異なるテーマを選ぶこと。**

**テーマ例（自由に選んでOK）:**
- 「2025年のSaaS業界トレンドと成長分野」
- 「AIを活用した営業プロセスの自動化事例」
- 「日本企業のDX推進における課題と成功パターン」
- 「リモートワーク時代のエンゲージメント施策」

**手順:**

1. https://chatgpt.com または https://gemini.google.com を開く
2. Deep Research モードを選択する
3. テーマに関するプロンプトを入力する:

```
[選んだテーマ] について、以下の観点で包括的にリサーチしてください:
1. 現状の概要
2. 主要なトレンドとデータ
3. 具体的な事例（企業名・数値を含む）
4. 課題と機会
5. 今後の予測

ソースURLも可能な限り含めてください。
```

4. 生成されたレポートを保存する

---

### 課題2: ファクトチェックログを作成する

**AI の出力を鵜呑みにせず、1つずつ検証する。** これがハルシネーション（AIのもっともらしい嘘）対策の基本。

**ファクトチェックの手順:**

| ステップ | やること | 例 |
|---------|---------|-----|
| 1. 抽出 | AI出力から検証すべき情報を抜き出す | 「○○社の売上は前年比30%増」 |
| 2. ソース確認 | AIが提示したURLを実際に開く | URLをクリックして内容を確認 |
| 3. 裏取り | 一次ソース（公式サイト、決算資料、政府統計）で確認 | IR資料、官公庁の統計データ等 |
| 4. 判定 | 信頼度をA/B/Cで評価する | A=確認済み、B=概ね正確、C=未確認/疑問あり |

**ファクトチェックログの形式:**

```markdown
## ファクトチェックログ

### チェック項目1
- AI出力: 「○○市場は2025年に△△億円規模に成長」
- ソースURL（AI提示）: https://...
- ソース確認結果: リンク有効 / リンク切れ / 内容が異なる
- 一次ソース: [確認に使ったURL]
- 信頼度: A / B / C
- コメント: [確認結果の詳細]

### チェック項目2
...
```

**最低5項目以上のファクトチェックを行うこと。**

特に注意すべき情報:
- **数値**: 市場規模、成長率、シェア（AIが捏造しやすい）
- **固有名詞**: 企業名、人名、製品名（実在しない企業を出すことがある）
- **日付**: 「2024年に発表された」等（年が間違っていることが多い）
- **URL**: AIが生成したURLは存在しないことがある（必ずクリックして確認）

---

### 課題3: ソース引用付きリサーチレポートを作成する

ファクトチェック済みの情報をもとに、信頼性の高いリサーチレポートを作成する。

**レポートの構成:**

```markdown
# [テーマ名] リサーチレポート

## 概要
[テーマの概要を3-5行で]

## 主要な知見

### 1. [知見のタイトル]
[内容]
> 出典: [URL] (信頼度: A)

### 2. [知見のタイトル]
[内容]
> 出典: [URL] (信頼度: B)

...

## 注意事項
- 信頼度Cの情報: [一覧と理由]
- 未確認の情報: [一覧]

## 結論・所感
[自分の分析と業務への示唆]
```

---

## Git操作（Day4 の復習 + 実践）

```bash
# 研修リポジトリに移動
cd spec-ai-training

# 最新を取得
git pull origin main

# ブランチを作成
git checkout -b training/day-05-research-factcheck
```

以下のような表示が出れば成功:
```
Switched to a new branch 'training/day-05-research-factcheck'
```

```bash
# フォルダを作成
mkdir -p training/day-05

# (ファイルを作成・編集した後)

# ステージング
git add training/day-05/

# 確認
git status
```

以下のファイルが表示されればOK:
```
new file:   training/day-05/research-report.md
new file:   training/day-05/fact-check-log.md
new file:   training/day-05/daily-report.md
```

```bash
# コミット
git commit -m "docs: add Day5 research report with fact-check log"

# プッシュ
git push origin training/day-05-research-factcheck
```

**GitHubでPRを作成する:**
1. https://github.com/あなたのユーザー名/spec-ai-training を開く
2. 黄色いバナーの「Compare & pull request」をクリック
3. タイトル: `Day5: リサーチレポート + ファクトチェックログ`
4. テンプレートに記入して「Create pull request」

---

## ヒント

- Day3 では Deep Research を「体験」した。Day5 では AI 出力の「信頼性検証」に重点を置く
- ハルシネーション（もっともらしい嘘）は必ず発生する。「これは正しいか？」と疑う習慣をつける
- 複数ツールの出力を突き合わせるのも有効なファクトチェック手法（Day3 の比較体験が活きる）
- URL が切れていたら「このURLは存在しなかった」とログに記録する。それ自体がハルシネーションの証拠

## 提出方法

1. 以下のファイルを `training/day-05/` に配置:
   - `research-report.md` — ソース引用付きリサーチレポート
   - `fact-check-log.md` — ファクトチェックログ（5項目以上）
   - `daily-report.md` — 日報
2. `git add` → `git commit` → `git push`
3. GitHub で PR を作成
4. Slack で「Day5 PR作成しました: [PR の URL]」と報告

## 理解度チェック（クイズ）

- `quizzes/index.html` をブラウザで開く
- 自分の名前を入力する
- 「Day5」を選択してクイズを受ける
- 100点になるまで何度でも再受験可能
- 100点の画面をスクリーンショットして保存する（PR提出時に添付）

## 早期完了者向け追加課題

- 同一テーマで Gemini Deep Research と ChatGPT Deep Research の出力を比較する
- 両方の出力に対してファクトチェックを実施し、以下を分析:
  - どちらがソースURLを多く提示するか
  - どちらのURLが有効率が高いか
  - 数値の正確性に差はあるか
- 成果物: `training/day-05/deep-research-comparison.md`

## 参考リソース

- [AI ハルシネーションとは（Google Cloud）](https://cloud.google.com/discover/what-are-ai-hallucinations)
- [ファクトチェックの基本（FIJ）](https://fij.info/introduction)
- Day3 の ChatGPT vs Claude 比較表（自分の成果物を参照）
- `CONTRIBUTING.md` — PR作成の規約
