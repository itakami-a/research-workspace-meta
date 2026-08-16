# Research Workspace

研究、AI支援作業、知識、計算実行環境を役割別に管理するためのワークスペースです。

## 最初に読むもの

1. `AGENTS.md` — AIを含む作業者が守る絶対的な境界
2. `_ai/rules/WORKSPACE_POLICY.md` — ディレクトリの役割と運用
3. `_ai/MIGRATION_STATUS.md` — 旧 `dev` からの移行状況
4. `_ai/bootstrap/SETUP_SECOND_PC.md` — 別PCで再現する方法

## ディレクトリの役割

- `_ai/`：AIの働き方、ルール、プロジェクトひな形、Skill原本、MCP設定例
- `notes/`：Obsidianなど、人間の思考・日記・Todo
- `knowledge/`：MVP、MARBLE、炉物理、作業手順の再利用可能な知識
- `work/`：自分が編集する日々の作業とプロジェクト
- `compute/`：MVP、MARBLEの入力、実行環境、計算結果
- `team/`：チーム資産。AIは読み取り専用
- `external/`：他者が作成した資産。AIは読み取り専用
- `personal/`：趣味・個人制作
- `sandbox/`：学習・短期的な試作
- `archive/`：現役ではない旧資産

## 基本ワークフロー

継続的な研究テーマでは、`_ai/templates/project/` をひな形として `work/projects/<project>/` を作ります。日々の作業は、そのプロジェクトの `sessions/YYYY-MM-DD_topic/` に置きます。所属先がまだ決まっていない作業は `work/inbox/YYYY/YYYY-MM-DD_topic/` で開始します。

作業後、再利用可能な知識は `knowledge/`、計算入力と出力は `compute/`、最終成果物はプロジェクトの `outputs/` に整理します。

## Git管理

このルートリポジトリは、共通ルール、テンプレート、知識文書、案内文書を2台のPCで同期するためのメタリポジトリです。`team/`、`external/`、生の計算結果、日々の一時作業はルートGitの対象外です。配下の独立Gitリポジトリは、それぞれ個別に管理します。
