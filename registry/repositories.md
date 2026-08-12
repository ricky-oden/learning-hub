# 4リポジトリ対応台帳

最終確認日: 2026-08-12

この台帳は、学習ハブと各アプリリポジトリの対応関係を管理します。各アプリ固有の詳細は複製せず、各リポジトリを正本として参照します。

## 確認方法と限界

各ローカルリポジトリで`git status -sb`、`git branch --show-current`、`git log --oneline --decorate -3`、`git remote get-url origin`、計画正本・statusを読み取り専用で確認しました。テスト、build、Docker、`git fetch`、外部接続は行っていないため、`origin/main`との一致はローカルに保存されたremote追跡参照に対する判定です。

| ID | ローカルパス | origin / branch | 現在HEAD | 計画正本commit | PLAN_VERSION / 要件数 | 現在フェーズ | worktree |
|---|---|---|---|---|---|---|---|
| `EC-V1` | `/Users/ricky_oden/demo/biyo_ec_full` | `https://github.com/ricky-oden/biyo_ec_full.git` / `main` | `c7437c32ab23660336fe7f2890e7bbbbeb04954e` | アプリ固有の計画正本なし。現在HEADを実装・監査の根拠として参照 | アプリ固有定義なし | 実装・監査後、コードリーディング進行中 | clean、ローカル`origin/main`と一致 |
| `TEA-V1` | `/Users/ricky_oden/demo/tea_manufacturing_system` | `https://github.com/ricky-oden/tea-manufacturing.git` / `main` | `fec3a1c7989930986a1ff98075a0ba245453a16c` | `90b825a4dbf1e81cf7594c7253caf8c42863772c` | `TEA-V1.0` / 19件 | Phase 0〜6完了。実装・ローカル検証完了、対話形式クイズ未開始 | clean、ローカル`origin/main`と一致 |
| `CONSTRUCTION-V1` | `/Users/ricky_oden/demo/construction_project_saas` | `https://github.com/ricky-oden/construction-saas.git` / `main` | `39dda70da23ee541249b5c02a3e4d38b16965606` | `39dda70da23ee541249b5c02a3e4d38b16965606` | `CONSTRUCTION-V1.0` / 26件 | Phase 0完了、上位計画に従いTEA-V1の基盤・代表的縦切り完了まで待機 | clean、ローカル`origin/main`と一致 |
| `AI-LEARNING-V1` | `/Users/ricky_oden/demo/ai_video_learning` | `https://github.com/ricky-oden/ai_video_learning.git` / `main` | `21ba1ae538c02986d78d407b54f5a032a2552fcf` | `21ba1ae538c02986d78d407b54f5a032a2552fcf` | `AI-LEARNING-V1.0` / 62件 | Phase 0完了、上位計画のTEA-V1、CONSTRUCTION-V1の順番に従い待機 | clean、ローカル`origin/main`と一致 |

## 正本の境界

- アプリ固有の計画、仕様、実装状況、検証記録、クイズ回答原文は各アプリリポジトリで管理する。
- この台帳には識別情報、参照先、確認時点の要約だけを記録する。
- HEAD、計画正本commit、PLAN_VERSION、要件数、現在フェーズ、branch、remote、worktree状態を再確認した場合は確認日と値を更新する。
