# 次期3リポジトリ構築準備

このディレクトリは、現在の美容サロン向けECとは別に構築する3システムについて、Gitリポジトリ作成前に確定できる事項を管理する一時的な引き継ぎ資料です。

対象は次の3システムです。

- お茶製造管理システム
- 建設業向け案件管理SaaS
- 美容師向け動画教育・AI学習支援サービス

## 現在の停止位置

各リポジトリの作成はユーザーが行います。そのため、現在は次を実行しません。

- Gitリポジトリの初期化
- GitHubリモートの作成・接続
- アプリケーションのscaffold
- 依存関係のインストール
- Docker imageのbuild
- PostgreSQL volumeの作成
- GitHub Actionsの作成・実行
- 外部APIの呼び出し

リポジトリ作成後は、[repository-handoff-checklist.md](repository-handoff-checklist.md)に沿って、1リポジトリずつ構築を開始します。

## この資料の扱い

- [master-plan.md](master-plan.md)を3案件共通の承認済み基準とする。
- [environment-blueprints.md](environment-blueprints.md)は初期環境の設計基準とする。
- [plan-governance.md](plan-governance.md)に反する計画変更をCodexが独断で行わない。
- 実際のリポジトリが作成されたら、案件固有部分を各リポジトリの`docs/implementation-plan.md`へ移す。
- 移植後も、このECリポジトリを3案件の実装リポジトリとして扱わない。

