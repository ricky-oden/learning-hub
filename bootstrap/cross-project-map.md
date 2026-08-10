# 4システム共通知識マップ

この表は1周目で用語の違いに迷わないための初期地図である。実装後に実在するクラス、関数、APIパスを追記する。

| 役割 | EC | 次期FastAPI系 | 標準・一般概念 |
|---|---|---|---|
| ブラウザ内UI | React＋Vite | React＋ViteまたはNext.js | UI、state、イベント、再レンダリング |
| 画面ルーティング | React Router | Next.js App Routerなど | URLと画面の対応 |
| HTTP client | Axios | 計画時に確定 | HTTP request生成 |
| サーバー状態 | Context＋`useEffect` | React Query／TanStack Query | 取得、cache、再取得、loading、error |
| フォーム | React state | React Hook Form | 入力状態、検証、送信 |
| backend routing | Django `urls.py` | FastAPI router | HTTP pathと処理の対応 |
| request/response schema | DRF Serializer | Pydantic model | 入力検証とJSON変換 |
| endpoint処理 | DRF APIView | FastAPI path operation | request受付とresponse生成 |
| 業務ロジック | service関数 | service/use-case層 | 業務ルール、取引境界 |
| ORM | Django ORM | SQLAlchemy | object操作とSQLの橋渡し |
| migration | Django migration | Alembic | DB schema変更履歴 |
| DB | PostgreSQL | PostgreSQL／pgvector | 永続化、制約、transaction、lock |
| frontend test | Jest＋RTL | Jest/Vitest＋RTL | component単体・結合テスト |
| backend test | pytest-django | pytest | API、service、DBテスト |
| E2E | 手動総合確認中心 | Playwright | 実ブラウザを含む導線検証 |
| 実行環境 | Docker Compose | Docker Compose | service分離と再現可能な環境 |

## 案件固有の中心概念

| システム | 中心概念 |
|---|---|
| EC | 匿名・会員カート、認証、在庫ロック、冪等注文、紹介割引 |
| お茶製造 | 製造状態遷移、原料・製品在庫、設備、CSV取込、集計整合性 |
| 建設SaaS | 案件・工程期間、ガント、カンバン、楽観的更新、担当者・権限 |
| AI学習支援 | 字幕分割、embedding、類似検索、根拠付き生成、stream、評価 |

