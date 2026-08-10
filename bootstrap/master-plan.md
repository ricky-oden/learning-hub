# 4システム横断学習マスタープラン

PLAN_VERSION: `CAREER-SYSTEMS-V1`

## 目的

4つのシステムを暗記するのではなく、異なるフレームワークや命名の間で同じ役割を見つけられる状態を目指す。

1周目は各システムの全体地図を作り、理解度を0から2以上へ引き上げる。2周目以降に、共通概念と案件固有の処理を結び付け、説明とコード追跡の精度を上げる。

## 対象システム

### EC-V1 美容サロン向けEC・会員制サイト

- 状態: 実装・Docker/PostgreSQL検証済み、コードリーディング進行中
- 主な技術: React、React Router、Axios、Django REST Framework、PostgreSQL、Jest、pytest、Docker
- 主な学習対象: CSR、REST API、Token認証、匿名・会員カート、トランザクション、行ロック、冪等注文

### TEA-V1 お茶製造管理システム

- 状態: リポジトリ作成待ち
- 主な技術: React、React Query、React Hook Form、FastAPI、SQLAlchemy、PostgreSQL、Jest、pytest、Docker、GitHub Actions
- 業務範囲: 原料入荷、製造指示、工程、設備、在庫、出荷、集計、マスタ、CSV取込
- 中心課題: 製造ステータス遷移、操作制御、在庫更新、CSV入力検証、統一APIエラー

### CONSTRUCTION-V1 建設業向け案件管理SaaS

- 状態: リポジトリ作成待ち
- 主な技術: Next.js、React、TanStack Query、React Hook Form、FastAPI、SQLAlchemy、PostgreSQL、Vitest、Playwright、pytest、Docker、GitHub Actions
- 業務範囲: 案件、顧客、物件、工程、担当者、進捗、ガントチャート、カンバン、変更履歴
- 中心課題: 検索条件管理、期間計算、楽観的更新と失敗時復元、複数担当者、権限・状態制御

### AI-LEARNING-V1 美容師向け動画教育・AI学習支援サービス

- 状態: リポジトリ作成待ち
- 主な技術: Next.js、React、FastAPI、PostgreSQL、pgvector、OpenAI API、Vitest、Playwright、pytest、Docker、GitHub Actions
- 業務範囲: 動画教材、字幕処理、ベクトル検索、質問応答、根拠・再生位置、ストリーミング、評価
- 中心課題: RAG、根拠不足時の回答抑止、教材外質問の制御、会員・管理者権限、AI品質評価
- 注意: 外部API利用と課金が発生し得る処理は、明示承認前に実行しない。学習用fake providerを先に用意する。

## 実施順

1. ユーザーが3つのローカルGitリポジトリとリモートを作成する。
2. お茶製造管理の計画を照合し、基盤と代表的な縦切り導線を実装する。
3. 建設SaaSの計画を照合し、基盤と代表的な縦切り導線を実装する。
4. AI学習支援の計画を照合し、fake providerを使った基盤と代表的なRAG導線を実装する。
5. 各リポジトリで全体地図を優先した1周目クイズを行う。
6. 4システムの共通概念を横断復習する。
7. 弱点だけを2周目のコード追跡・テスト読解・障害調査問題で補う。

## 1周目の完成条件

各リポジトリで、少なくとも次を自分の言葉で説明できる状態にする。

- ブラウザからDBまたは外部境界までの主要な1往復
- frontend、backend、databaseの責務
- URL、Viewまたはrouter、schema、service、ORM、DBのつながり
- 代表的なstate変更と再レンダリング
- 正常系1本と重要な異常系1本
- その案件固有の中心的な業務ルール
- テストが実物とmockのどこまでを確認しているか
- Docker Compose上のサービス間接続

## 変更禁止事項

明示承認なしに次を変更しない。

- 採用技術の大分類
- システムの業務範囲
- 学習順序の大幅な変更
- 外部有料サービスの利用
- 実決済や本番デプロイの追加
- 自動push、PR作成、GitHub Actions自動トリガー

