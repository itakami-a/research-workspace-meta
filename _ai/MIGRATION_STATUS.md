# Migration Status

更新日: 2026-08-16

## 完了

- 新しいルート `C:\Users\withd\workspace` の設計と共通ルールを作成
- 旧 `dev\git-tshinohara` を `workspace\external\tshinohara` へ移動
- 旧 `dev\team` を `workspace\team` へ移動

## 移動していないもの

ユーザーから移動権限が与えられていないため、次は旧 `C:\Users\withd\dev` に残しています。

- `personal/`
- `research/`
- `sandbox/`

これらは内容を分類し、移動対象の対応表を確認してから段階的に移行します。

## 移動時に確認された既存Git状態

- `external/tshinohara` 配下の `CompactEditor`、`IndexHandler`、`OutputIndexer`、`OutputPlotter`、`ParaText` には未追跡の `build/` が存在していた
- `team/Study-on-Tube-Fast-Reactor` には698件の既存差分があり、主に追跡済みファイルの削除として表示されていた
- 移行では各リポジトリ内部を変更せず、親ディレクトリを丸ごと移動した

この状態をユーザーの確認なしに復元、削除、コミットしてはいけません。
