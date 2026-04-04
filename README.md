# Spec AI Training

AIオンボーディング研修の公開リポジトリ。

## 目的

- 研修資料をプライベートな業務リポジトリから分離する
- 各メンバーがこのリポジトリをcloneして自走できる状態を作る
- 日次完了フローをGitHub運用で標準化する

## 対象範囲

- Day4-Day13 のカリキュラム
- 学習リソース
- 学習運用ルール（レビュー、クイズ、完了判定）

## 日次必須ルール（Git/GitHubレッスン後）

Day5以降の1日完了条件は以下。

1. 当日成果物を個人リポジトリへPush（`training/day-xx/`）
2. PR作成
3. GitHub -> Slack 通知を確認
4. レビューコメントを反映
5. PRをMerge

Mergeされていない場合、その日は未完了扱い。

## クイズゲート

- 理解度チェックは Google Forms の自動採点を利用
- 合格基準は100点
- 当日内の再受験は無制限

## リポジトリ構成

- `curriculum.md`: 日別カリキュラム
- `resources.md`: 参考教材（動画、記事、公式ドキュメント）
- `learning-infrastructure.md`: 実行ループ、レビュー運用、クイズ運用
- `CONTRIBUTING.md`: 運用ルールとPRルール
- `templates/`: 日次アウトプット/PR本文/日報テンプレート
- `references/`: テンプレートは追跡対象、`references/farleap-context.local.md` のみgitignore対象

## ローカル限定コンテキスト

業務上の内部コンテキストが必要な場合は、ローカル専用ファイルを利用する。

- `references/farleap-context.local.md`（gitignore）

テンプレートは以下を使用。

- `references/farleap-context.example.md`
