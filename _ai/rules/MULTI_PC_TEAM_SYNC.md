# 複数PCでのteamリポジトリ同期

## 目的

デスクトップPCとノートPCで同じteamリポジトリを扱う際、未コミット変更の上書きや履歴の分岐を防ぎながら、手動確認を最小化する。

## 基本方針

- GitHub上のリポジトリを端末間同期の正本とする。
- フォルダの直接コピーや上書きで同期しない。
- `team/**` はAI読み取り専用とし、pull、commit、push、merge、checkoutなどの変更操作は、その作業ごとにユーザーの明示承認を得る。
- 読み取り専用の状態確認は `team-sync-check` Skillで標準化する。
- 一方のPCから、もう一方のPCにある未コミット変更は確認できない。各PCで状態確認を実行する。

## ブランチ構成

- 共有安定branch: `itakami`
- デスクトップ作業branch: `itakami/desktop`
- ノート作業branch: `itakami/notebook`

PC固有branch名は運用開始前にGitHub上の既存branchと衝突しないことを確認する。共有branchへの統合はPRまたは明示承認されたmergeで行う。

## 作業開始時

1. `.local/DEVICE.md` から端末を確認する。
2. origin、branch、HEAD、upstream、`git status` を読み取り専用で取得する。
3. 未コミット変更、未追跡ファイル、ahead/behind、履歴分岐を確認する。
4. dirtyまたは分岐状態なら同期操作を止め、変更の所有者と方針を確認する。
5. cleanでfast-forward可能な場合だけ、ユーザーへpullの承認を求める。

## 作業終了時

1. `git status` と差分を確認する。
2. 変更内容、検証結果、未解決事項を報告する。
3. commit、push、PR作成は対象と操作について明示承認を得てから行う。
4. 未commitまたは未pushの作業を残す場合は、端末名、branch、HEAD、残作業を記録する。

## 同じファイルを両PCで編集した場合

- どちらかを推測で正として上書きしない。
- 各PCの変更をそれぞれのPC固有branchへ保全する。
- GitHubへpushした後、共有branchへの統合時に競合を一件ずつ解決する。
- 解決前にreset、checkout、stash、cleanを実行しない。

## 自動化してよい範囲

- 定期的なbranch、HEAD、status、ahead/behindの読み取り
- dirty、behind、分岐、誤branchの通知
- fast-forward可能性の判定

自動pull、commit、push、merge、競合解決は行わない。
