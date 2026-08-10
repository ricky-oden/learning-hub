# Career Systems Learning Hub

このリポジトリは、4つの学習用システムを横断管理する学習ハブです。アプリケーションコードは配置せず、全体計画、計画変更管理、共通知識マップ、学習進捗、リポジトリ間の対応関係を管理します。

## 対象システム

- `EC-V1`: 美容サロン向けEC・会員制サイト
- `TEA-V1`: お茶製造管理システム
- `CONSTRUCTION-V1`: 建設業向け案件管理SaaS
- `AI-LEARNING-V1`: 美容師向け動画教育・AI学習支援サービス

## 正本と役割

| 資料 | 役割 |
|---|---|
| [`bootstrap/master-plan.md`](bootstrap/master-plan.md) | 承認済み上位計画 `CAREER-SYSTEMS-V1` |
| [`bootstrap/plan-governance.md`](bootstrap/plan-governance.md) | 計画固定と変更管理の原則 |
| [`bootstrap/environment-blueprints.md`](bootstrap/environment-blueprints.md) | 次期システムの初期環境設計基準 |
| [`bootstrap/cross-project-map.md`](bootstrap/cross-project-map.md) | 4システムの共通知識マップ |
| [`registry/repositories.md`](registry/repositories.md) | リポジトリID、パス、remote、確認時点の対応台帳 |
| [`status/portfolio-status.md`](status/portfolio-status.md) | 4システムの横断状態 |
| [`quiz-progress-index.md`](quiz-progress-index.md) | コードリーディング学習の横断索引 |
| [`governance/decision-log.md`](governance/decision-log.md) | 承認済みの横断決定 |

各アプリ固有の実装計画、実装状況、検証証跡、詳細仕様、クイズ回答原文は各アプリリポジトリを正本とします。このハブには全文を複製せず、横断管理に必要な要約、参照先、確認時点だけを記録します。

## 状態記録の原則

- 計画、実装、検証、学習進捗を分離して記録する。
- `実装済み`、`検証済み`、`完了済み`は根拠なしに使用しない。
- リポジトリ確認結果には確認日、ブランチ、コミットを付ける。
- `git fetch`を行っていない確認では、ローカルに保存されたremote追跡参照との一致として扱う。
- 上位計画の変更だけを`PROPOSED_CHANGE`として提示し、明示承認後に反映する。
- 通常の正本構造整備、状態更新、参照先更新を上位計画変更と混同しない。

作業時の詳細な制約は[`AGENTS.md`](AGENTS.md)に従います。
