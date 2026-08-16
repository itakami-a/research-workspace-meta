# 別PCでのセットアップ

## 目的

2台目のPCでも同じルール、テンプレート、知識構造を再現し、Codexが同じ境界を理解できるようにします。

## 手順

1. ユーザー領域に `workspace` を用意する。
2. このメタリポジトリを `workspace` としてcloneする。
3. 最初にルートの `AGENTS.md` と `README.md` を読む。
4. `team/` の各リポジトリを個別にcloneする。
5. `external/tshinohara/` の各リポジトリを個別にcloneする。
6. Obsidian Vaultを `notes/obsidian-vault/` にcloneする。
7. 必要な自作Skillを `_ai/skills-src/` から、そのCodex環境が認識する標準のSkill領域へ導入する。
8. `_ai/mcp/` の説明に従ってMCPを設定する。秘密情報はリポジトリへ保存しない。

## 注意

- `team/` と `external/` はルートGitには含まれません。
- `compute/**/runs/` と `compute/**/cases/` は端末ローカルを基本とします。
- Gitで同期する前に `git status` と差分を確認します。
- ハードコードした絶対パスではなく、各PCのユーザーディレクトリを基準にします。

## 未完了

このメタリポジトリのリモートURLはまだ設定されていません。GitHubに新しいプライベートリポジトリを作成した後、`origin` を登録してpushします。
