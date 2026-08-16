# Repository Manifest

別PCで個別にcloneするリポジトリの記録です。`team/` と `external/` はAI読み取り専用です。

## Team

- `team/Study-on-Tube-Fast-Reactor`
  - origin: `git@github.com:tshinohara0/Study-on-Tube-Fast-Reactor.git`
  - 移動時のbranch: `itakami`

## External / tshinohara

- `external/tshinohara/AutoRunner` — `git@github.com:tshinohara0/AutoRunner.git`
- `external/tshinohara/CompactEditor` — `git@github.com:tshinohara0/CompactEditor.git`
- `external/tshinohara/IndexHandler` — `git@github.com:tshinohara0/IndexHandler.git`
- `external/tshinohara/OutputIndexer` — `git@github.com:tshinohara0/OutputIndexer.git`
- `external/tshinohara/OutputPlotter` — `git@github.com:tshinohara0/OutputPlotter.git`
- `external/tshinohara/ParaText` — `git@github.com:tshinohara0/ParaText.git`
- `external/tshinohara/ShinoHydroV2` — `git@github.com:tshinohara0/ShinoHydroV2.git`
- `external/tshinohara/Nudec` — `git@github.com:tshinohara0/Nudec.git`

## Notebook migration notes

- `notebook-withd` では `team/` と `external/tshinohara/` はまだ新workspaceへ移植されていない。
- 旧配置は `C:\Users\withd\dev\team` と `C:\Users\withd\dev\git-tshinohara`。
- `Nudec` はノートPC上で `tshinohara0/Nudec` のGitリポジトリとして確認され、`external/tshinohara/Nudec` に正式分類する。
- `LatticeEditor` のGit追跡部分は外部リポジトリだが、未追跡の `programs/itakami/*.py` 4件が混在する。新workspaceへ移植せず、旧 `dev` 側に保全する。
- 各リポジトリ内の `build/lib` は生成物として移植判断の対象外にする。ただし読み取り専用資産内では削除しない。
