# Gitリポジトリ作成後の引き継ぎチェックリスト

ユーザーが1つのリポジトリを作成するたびに、そのリポジトリだけを対象として以下を実施する。3リポジトリを同時にscaffoldしない。

## ユーザーから受け取る情報

- ローカルの絶対パス
- GitHub remote URL
- repository名
- privateまたはpublic
- default branch名
- 対応する計画ID: `TEA-V1`、`CONSTRUCTION-V1`、`AI-LEARNING-V1`のいずれか

## 最初の読み取り確認

```bash
pwd
git status
git remote -v
git branch --show-current
git log --oneline --decorate -5
```

空リポジトリであること、意図したremoteであること、秘密情報が存在しないことを確認する。

## 実装前に作る資料

- `AGENTS.md`
- `README.md`
- `.gitignore`
- `.env.example`
- `docs/implementation-plan.md`
- `docs/status.md`
- `docs/decision-log.md`
- `docs/system-overview.md`
- `docs/screen-list.md`
- `docs/api-specification.md`
- `docs/data-model.md`
- `docs/test-strategy.md`
- `docs/code-reading-guide.md`
- `docs/skill-sheet-mapping.md`

この時点では、元スキルシートにある経験を無条件に実装済みと記載しない。要件と実装済み状態を分ける。

## 環境構築の開始条件

- ユーザーが案件固有の実装計画を承認している
- Node.js、Python、PostgreSQLのバージョンが確定している
- host portとCompose project名が確定している
- package managerとlockfile方針が確定している
- CIの初期triggerが`workflow_dispatch`である
- 外部API、課金、秘密情報の扱いが確定している

## 基盤作成後の最低検証

- frontend test runnerが起動する
- frontend production buildが成功する
- backend test runnerがPostgreSQL test DBへ接続する
- backend system/startup checkが成功する
- migration差分が管理されている
- `docker compose config --quiet`が成功する
- frontendからbackend health APIへ到達できる
- backendからPostgreSQLへ到達できる
- `.env`、DBファイル、cache、build生成物がGit管理されていない

## コミットとpush

コミットは機能・責務単位に分ける。pushはユーザーから個別に明示された場合だけ行う。

