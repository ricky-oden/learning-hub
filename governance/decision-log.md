# 横断決定ログ

このファイルには、学習ハブ全体に関してユーザーが明示承認した決定だけを追記します。各アプリ固有の決定は各アプリリポジトリを正本とします。

## DECISION-001: 学習ハブの正本構造を整備する

- 決定日: 2026-08-10
- 状態: 承認・反映済み
- 対象: 学習ハブの文書構造
- 決定:
  - ルート`README.md`とハブ専用`AGENTS.md`を追加する。
  - `registry/repositories.md`、`status/portfolio-status.md`、`governance/decision-log.md`を追加する。
  - `bootstrap/README.md`に残る、学習ハブの現在の役割と合わない古い表現を限定修正する。
  - 4アプリリポジトリを読み取り専用で確認し、詳細を複製せず台帳とstatusへ実態を記録する。
- 変更しないもの:
  - `bootstrap/master-plan.md`
  - `CAREER-SYSTEMS-V1`の業務範囲、技術構成、実施順
  - `quiz-progress-index.md`の配置
  - 各アプリのコード、GitHub設定
- 承認根拠: ユーザーがPC-001を上記範囲に限定して明示承認。

## DECISION-002: PROPOSED_CHANGEの適用範囲

- 決定日: 2026-08-10
- 状態: 承認・反映済み
- 決定: `PROPOSED_CHANGE`は上位計画そのものを変更する場合だけ使用する。正本構造の整備、事実に基づく状態更新などの通常の文書作業と、上位計画の変更を混同しない。
- 影響: `bootstrap/master-plan.md`の無断変更禁止は維持しつつ、承認範囲内の通常文書保守を別管理する。
