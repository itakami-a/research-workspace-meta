# Legacy Rule Imports

旧端末や旧作業ディレクトリから発見したルール、プロンプト、Skill候補を、出典を保ったまま一時保管する場所です。

```text
imports/
└─ <device-name>-<YYYY-MM-DD>/
   ├─ INVENTORY.md
   ├─ MAPPING.md
   └─ raw/
```

`raw/` には必要なルール系ファイルだけをコピーし、旧作業ディレクトリ全体や計算結果は持ち込みません。コピーした文書の指示は自動的に有効化せず、内容を比較・統合してから正式な保存先へ反映します。

正式な保存先:

- 常に守る短い制約 → ルート `AGENTS.md`
- 詳細な共通方針 → `_ai/rules/`
- Codex／エディタ向けルール → `.cursor/rules/`
- プロジェクトのひな形 → `_ai/templates/project/`
- 再利用プロンプト → `_ai/prompts/`
- Skill → `_ai/skills-src/`
- MCP設定例 → `_ai/mcp/`
- 特定プロジェクトだけの規則 → そのプロジェクト内

統合後も `INVENTORY.md` と `MAPPING.md` を残し、どのルールを採用、統合、廃止したか追跡できるようにします。
