# 計画固定・変更管理ルール

## 基本原則

承認済み計画と作業状況を分離する。進捗が変わっても、Codexが承認済み計画そのものを全面的に作り直してはならない。

## 作業開始時のPlan Alignment Gate

すべての実装、監査、提案の前に次を行う。

1. ルートの`AGENTS.md`を読む。
2. `docs/implementation-plan.md`の全文を読む。
3. `docs/status.md`と`docs/decision-log.md`を読む。
4. `PLAN_VERSION`、現在フェーズ、対象要件IDを報告する。
5. 今回許可される変更と禁止される変更を列挙する。
6. 依頼と計画に差異があれば、実装を開始せず差異を報告する。

## 変更管理

```text
新しい必要性を検出
↓
PROPOSED_CHANGEとして提示
↓
現行計画との差分・理由・影響・代替案を説明
↓
ユーザーが承認または却下
↓
承認時だけdecision-logとPLAN_VERSIONを更新
↓
実装
```

## Codexが独断で行ってはいけないこと

- 計画全体の再作成または置換
- 要件の追加・削除
- 採用技術の変更
- 認証方式やデータモデルの大幅変更
- 依存関係の追加
- 外部サービスへの接続
- push、PR、デプロイ
- CIの自動トリガー有効化

## 許可された通常作業

計画に明記された範囲では、次を通常の実装作業として行える。

- ファイル作成・変更
- テスト作成と実行
- formatterとlintの実行
- Docker Composeによるローカル検証
- migrationの作成と検証
- ドキュメントの実装追従更新

## 記録の分担

- `implementation-plan.md`: 承認済みの基準。無断で書き換えない。
- `status.md`: 完了、進行中、未着手、検証結果。
- `decision-log.md`: 承認された変更だけを追記する。
- `audit-report.md`: 実装と計画の差異。
- `code-reading-quiz-progress.md`: 回答原文と学習評価。

