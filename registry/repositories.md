# 4リポジトリ対応台帳

確認日: 2026-08-10

この台帳は、学習ハブと各アプリリポジトリの対応関係を管理します。各アプリ固有の詳細は複製せず、各リポジトリを正本として参照します。

## 確認方法と限界

各ローカルリポジトリで`git status --short --branch`、`git branch --show-current`、`git remote -v`、`git log --oneline --decorate -5`、追跡ファイル一覧を読み取り専用で確認しました。`git fetch`や外部接続は行っていないため、`origin/main`との一致はローカルに保存されたremote追跡参照に対する判定です。

| ID | ローカルパス | origin | branch | 確認時HEAD | worktree | 固有資料の現在地 |
|---|---|---|---|---|---|---|
| `EC-V1` | `/Users/ricky_oden/demo/biyo_ec_full` | `https://github.com/ricky-oden/biyo_ec_full.git` | `main` | `c7437c3` | clean、ローカル`origin/main`と一致 | README、実装・監査・仕様・クイズ資料あり |
| `TEA-V1` | `/Users/ricky_oden/demo/tea_manufacturing_system` | `https://github.com/ricky-oden/tea-manufacturing.git` | `main` | `adb43fa` | clean、ローカル`origin/main`と一致 | READMEは空、固有計画資料なし |
| `CONSTRUCTION-V1` | `/Users/ricky_oden/demo/construction_project_saas` | `https://github.com/ricky-oden/construction-saas.git` | `main` | `9884986` | clean、ローカル`origin/main`と一致 | READMEはリポジトリ名のみ、固有計画資料なし |
| `AI-LEARNING-V1` | `/Users/ricky_oden/demo/ai_video_learning` | `https://github.com/ricky-oden/ai_video_learning.git` | `main` | `bad13d5` | clean、ローカル`origin/main`と一致 | READMEは空、固有計画資料なし |

## 正本の境界

- アプリ固有の計画、仕様、実装状況、検証記録、クイズ回答原文は各アプリリポジトリで管理する。
- この台帳には識別情報、参照先、確認時点の要約だけを記録する。
- HEAD、branch、remote、worktree状態を再確認した場合は確認日と値を更新する。
