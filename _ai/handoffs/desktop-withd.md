# Desktop Handoff

更新日: 2026-08-17
端末: `desktop-withd`
共有メタリポジトリの基準commit: `a5d52c7`

## 完了

- `workspace` の共通ルール、テンプレート、同期手順をGitHubで共有した
- `external/tshinohara` と `team/Study-on-Tube-Fast-Reactor` をデスクトップ側で新構成へ移動した
- ノート側のteam同期ワークフローを `main` へ統合した

## 現在の状態

- `team/**` と `external/**` はAI読み取り専用
- デスクトップ側teamリポジトリには、移動前から存在する698件のGit差分がある。内容を復元、削除、commitしない
- 旧 `dev/research`、`dev/personal`、`dev/sandbox` は未移行

## 次の一手

- ノート側はGitHubの最新 `main` を確認し、自端末のhandoffを更新する
- 旧 `research` から重要ルールを調査し、承認後に分類・移植する

## 承認が必要な操作

- `team` または `external` の変更
- 旧 `research`、`personal`、`sandbox` の移動または削除
- Gitのpull、merge、reset、clean、commit、push
