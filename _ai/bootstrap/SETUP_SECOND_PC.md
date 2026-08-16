# 別PCでのセットアップ

## 目的

2台目のPCでも同じルール、テンプレート、知識構造を再現し、Codexが同じ境界を理解できるようにします。

## 手順

1. ユーザー領域に `workspace` を用意する。
2. このメタリポジトリを `workspace` としてcloneする。
3. `_ai/bootstrap/DEVICE.example.md` を参考に、ノート固有の `.local/DEVICE.md` を作る。
4. 最初にルートの `AGENTS.md` と `README.md` を読む。
5. `team/` の各リポジトリを個別にcloneする。
6. `external/tshinohara/` の各リポジトリを個別にcloneする。
7. Obsidian Vaultを `notes/obsidian-vault/` にcloneする。
8. 必要な自作Skillを `_ai/skills-src/` から、そのCodex環境が認識する標準のSkill領域へ導入する。
9. `_ai/mcp/` の説明に従ってMCPを設定する。秘密情報はリポジトリへ保存しない。
10. 旧 `research` からルールを移植する場合は、`MIGRATE_ANOTHER_PC.md` に従い、最初は読み取り専用で候補一覧を作る。
11. Gitリポジトリの版が異なる場合は、`REPO_RECONCILIATION.md` に従い、両端末の状態を比較してから同期方法を決める。

## 注意

- `team/` と `external/` はルートGitには含まれません。
- `compute/**/runs/` と `compute/**/cases/` は端末ローカルを基本とします。
- Gitで同期する前に `git status` と差分を確認します。
- ハードコードした絶対パスではなく、各PCのユーザーディレクトリを基準にします。

## 未完了

このメタリポジトリのリモートURLはまだ設定されていません。GitHubに新しいプライベートリポジトリを作成した後、`origin` を登録してpushします。
