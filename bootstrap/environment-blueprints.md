# 初期環境ブループリント

この文書はGitリポジトリ作成後に環境構築を開始する際の基準であり、現時点ではコマンドを実行しない。

## 共通原則

- 各アプリは独立したGitリポジトリ、Docker Compose project、`.env`、PostgreSQL volumeを持つ。
- Node.js、Python、DBのバージョンは各計画作成時に固定し、lockfileを管理する。
- production依存とdevelopment/test依存を分離する。
- 実`.env`はGit管理外とし、`.env.example`には開発用の例だけを置く。
- DBは原則としてComposeネットワーク内の`db:5432`へ接続する。
- CIは初期状態では`workflow_dispatch`だけとし、無料枠と支出上限の確認前に自動トリガーを有効化しない。
- formatter、lint、test、build、migration checkを再現可能なコマンドとしてREADMEへ記載する。

## 推奨識別子とポート

| システム | Compose project | frontend | backend | DB内部接続 |
|---|---|---:|---:|---|
| EC | `biyo-ec` | 5173 | 8000 | `db:5432` |
| お茶製造 | `tea-manufacturing` | 5174 | 8001 | `db:5432` |
| 建設SaaS | `construction-saas` | 3000 | 8002 | `db:5432` |
| AI学習支援 | `ai-video-learning` | 3001 | 8003 | `db:5432` |

ホストポートは同時起動時の混乱を避けるための初期案である。変更には計画差分の記録を必要とするが、アプリの業務仕様変更には当たらない。

## TEA-V1

### 想定サービス

- `frontend`: React、TypeScript、Vite、React Query、React Hook Form
- `backend`: Python、FastAPI、SQLAlchemy、Alembic
- `db`: PostgreSQL

### 最初の縦切り導線

```text
製造指示一覧
→ FastAPI一覧API
→ SQLAlchemy
→ PostgreSQL
→ ステータス表示
→ 許可された状態変更
→ 在庫更新
```

CSV取込は基盤完成後に独立した機能単位として追加する。

## CONSTRUCTION-V1

### 想定サービス

- `frontend`: Next.js、React、TypeScript、TanStack Query、React Hook Form
- `backend`: Python、FastAPI、SQLAlchemy、Alembic
- `db`: PostgreSQL

### 最初の縦切り導線

```text
案件一覧
→ 検索・絞り込み・ページング
→ FastAPI一覧API
→ SQLAlchemy
→ PostgreSQL
→ 案件詳細
```

ガントチャート、カンバン、楽観的更新は一覧・詳細・権限モデルが確立してから追加する。

## AI-LEARNING-V1

### 想定サービス

- `frontend`: Next.js、React、TypeScript
- `backend`: Python、FastAPI
- `db`: PostgreSQL、pgvector extension
- `ai-provider`: 最初は決定論的なfake provider。実OpenAI API接続は明示承認後。

### 最初の縦切り導線

```text
質問入力
→ FastAPI質問API
→ fake検索結果
→ 根拠付き回答
→ ストリーミング表示
→ 関連動画と再生位置
→ 利用者評価
```

字幕分割、embedding、pgvector検索、実モデル接続は境界を分離し、段階的に置き換えられる設計にする。

## Git作成後に確定する項目

- 実際のローカルパス
- GitHub remote URLと公開範囲
- package名、Python package名、DB名
- Node.jsとPythonの固定バージョン
- package manager
- backend依存管理方式
- 認証方式
- 各サービスのhealthcheck
- テストDBの起動方法
- AI学習支援で実APIを使用するか、最後までfakeで完結させるか

