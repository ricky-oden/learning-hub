# 4システム横断ステータス

最終確認日: 2026-08-12
上位計画: `CAREER-SYSTEMS-V1`

このファイルは事実に基づく現在地を記録します。承認済み計画そのものは`bootstrap/master-plan.md`を正本とし、このファイルの更新によって計画を変更しません。

## 現在地

| ID | 計画正本 | 現在フェーズ | 実装・検証状態 | 学習状態 | 今回確認した根拠 |
|---|---|---|---|---|---|
| `EC-V1` | アプリ固有の計画正本、PLAN_VERSION、要件数の定義なし | 実装・監査後、コードリーディング進行中 | 実装あり。2026-08-04付の監査・READMEにDocker/PostgreSQL、pytest 32件、Jest 25件、Vite buildの成功記録あり。2026-08-12には再実行していない | 36問評価済み | HEAD `c7437c32ab23660336fe7f2890e7bbbbeb04954e`。コード、README、監査・クイズ資料を読み取り確認 |
| `TEA-V1` | `TEA-V1.0`、19件、計画正本commit `90b825a4dbf1e81cf7594c7253caf8c42863772c` | Phase 0〜6完了 | 全19件が計画済み・実装済み・ローカル検証済み | 対話形式クイズ未開始 | HEAD `fec3a1c7989930986a1ff98075a0ba245453a16c`。実装、テスト、正本資料、Phase 6 commit群を読み取り確認 |
| `CONSTRUCTION-V1` | `CONSTRUCTION-V1.0`、26件、commit `39dda70da23ee541249b5c02a3e4d38b16965606` | Phase 0完了。上位計画に従いTEA-V1の基盤・代表的縦切り完了まで待機 | 全26件は計画済み。アプリ実装・テスト・Dockerは未着手 | 未着手 | 現在HEADが計画正本commitと一致。`docs/implementation-plan.md`、`docs/requirements.md`、`docs/status.md`を読み取り確認 |
| `AI-LEARNING-V1` | `AI-LEARNING-V1.0`、62件、commit `21ba1ae538c02986d78d407b54f5a032a2552fcf` | Phase 0完了。上位計画のTEA-V1、CONSTRUCTION-V1の順番に従い待機 | 全62件は計画済み。アプリ実装・テスト・Dockerは未着手。OpenAI SDK、API key、実OpenAI API接続はなく、初期実装は決定論的fake providerの計画 | 未着手 | 現在HEADが計画正本commitと一致。`docs/implementation-plan.md`、`docs/requirements.md`、`docs/status.md`を読み取り確認 |

## 確認上の注意

- 今回は2026-08-12時点のローカルリポジトリを読み取り専用で確認し、テスト、build、Docker Composeは実行していない。
- EC-V1の`検証済み`は、2026-08-04付のリポジトリ内検証記録を根拠とする。今回の再検証を意味しない。
- EC-V1の監査資料には、GitHub Actions未実行、キーボード通し操作未完了、未使用Modalの操作不足など、明示的な未検証・未解決事項も記録されている。
- TEA-V1の`ローカル検証済み`は、確定HEADの記録にあるpytest 78件、Jest 55件、skip・xfail 0件、lint・format・build・migration・Compose・API確認の成功を根拠とする。今回ハブ同期時に再実行したものではない。
- TEA-V1のGitHub Actionsは`workflow_dispatch`限定の構造を静的検証済みだが、workflow本体は未実行である。
- TEA-V1.0では認証・権限、監査ログ、TLS、秘密情報管理、監視、バックアップ、production frontend配信runtime、production deploymentなどを対象外としており、実装完了に含めない。
- TEA-V1の実装完了は本人の学習・説明力の習得完了を意味しない。対話形式コードリーディングクイズは未開始である。
- 各リポジトリは確認時点でcleanかつローカル`origin/main`と一致していたが、外部接続を行っていないためGitHub上の最新状態は確認していない。
- クイズの詳細と集計は`quiz-progress-index.md`および各アプリ側の正本を参照する。

## 次の計画上の位置

`CAREER-SYSTEMS-V1`の実施順を変更せず、TEA-V1の実装完了後はCONSTRUCTION-V1を上位計画どおり進める段階です。
