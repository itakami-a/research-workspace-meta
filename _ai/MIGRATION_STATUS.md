# Migration Status

更新日: 2026-08-17

## 完了

- 新しいルート `C:\Users\withd\workspace` の設計と共通ルールを作成
- デスクトップPCで旧 `dev\git-tshinohara` を `workspace\external\tshinohara` へ移動
- デスクトップPCで旧 `dev\team` を `workspace\team` へ移動

## 端末別の移植状況

### desktop

- `external/tshinohara` と `team` は移動済みと記録されている。
- 移動時の既存差分は下記の記録を維持し、再確認なしに変更しない。

### notebook-withd

- 2026-08-17に `external/tshinohara` の9リポジトリをGitHubから新規cloneした。
- 2026-08-17に `team/Study-on-Tube-Fast-Reactor` の `itakami` branchをGitHubから新規cloneした。
- clone後、全リポジトリでorigin、branch、HEAD、upstream、cleanな作業ツリーを確認した。
- 旧資産は `C:\Users\withd\dev\git-tshinohara` と `C:\Users\withd\dev\team` に残っている。
- 旧 `research` 内の同名リポジトリを含め、team・tshinohara由来資産は読み取り専用とする。
- `Nudec` は `external/tshinohara/Nudec` に正式分類する。
- `LatticeEditor` のGit追跡部分は `external/tshinohara/LatticeEditor` へ新規cloneした。旧 `LatticeEditor/programs/itakami/*.py` の未追跡4件は移植せず、旧 `dev` 側に保全する。
- tshinoharaリポジトリ内の `build/lib` は生成物として移植対象から除外するが、削除しない。

## デスクトップPCで移動していないもの

ユーザーから移動権限が与えられていないため、次は旧 `C:\Users\withd\dev` に残しています。

- `personal/`
- `research/`
- `sandbox/`

これらは内容を分類し、移動対象の対応表を確認してから段階的に移行します。

## 移動時に確認された既存Git状態

- `external/tshinohara` 配下の `CompactEditor`、`IndexHandler`、`OutputIndexer`、`OutputPlotter`、`ParaText` には未追跡の `build/` が存在していた
- `team/Study-on-Tube-Fast-Reactor` には698件の既存差分があり、主に追跡済みファイルの削除として表示されていた
- 移行では各リポジトリ内部を変更せず、親ディレクトリを丸ごと移動した
- `team` の全6798ファイルは新しい場所へ移動済み。移動時に別プロセスが使用中だったため残った旧 `dev\\team` の空ディレクトリも、プロセス終了後に削除済み

この状態をユーザーの確認なしに復元、削除、コミットしてはいけません。
