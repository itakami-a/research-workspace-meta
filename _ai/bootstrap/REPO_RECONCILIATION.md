# Git Repository Reconciliation

## 原則

「新しいPCの方が新しいだろう」と推測せず、commit hashと作業ツリーを比較します。`git pull` は最初の調査手段ではありません。

## 読み取り専用インベントリ

各PCで次を記録します。

```text
path:
origin:
branch:
HEAD:
upstream:
status:
last commit:
owner: self | team | external
```

最初はローカル情報だけを収集します。リモートの最新状態を確認する `fetch` は作業ツリーを書き換えませんが、Git内部のremote-tracking refを更新するため、実行前にユーザーへ確認します。

## 判定

### 同じHEADで両方clean

そのまま利用できます。

### 片方だけ先に進んでおり、両方clean

originに先行commitがpush済みか確認し、遅れている端末をfast-forwardできるか判断します。

### 未コミット変更がある

変更内容と所有者を確認するまで同期しません。自分のリポジトリなら、バックアップbranchやcommitの方針を決めます。`team` と `external` はAIがcommit、stash、破棄しません。

### 両端末のcommit履歴が分岐している

両方のHEADを保存し、commit差分を比較します。どちらかを強制的に正とせず、merge、rebase、cherry-pickの選択をユーザーと決めます。

### external

原則としてoriginを正とし、新端末には再cloneします。ただし未追跡ファイルやローカル変更があるコピーは、確認前に削除しません。

### team

読み取り専用のまま状態を報告します。pullやbranch変更を含む操作には、その都度ユーザーの明示的な許可が必要です。

## 記録

比較結果は `_ai/imports/<device-date>/REPOSITORIES.md` に残します。各リポジトリについて、採用した基準、実施操作、最終HEADを記録します。
