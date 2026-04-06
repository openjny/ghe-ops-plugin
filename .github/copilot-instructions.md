# Copilot Instructions — github-enterprise-ops-plugin

GitHub Enterprise の管理・運用に関する知識とスキルを提供する VS Code Agent Plugin。

## プロジェクト概要

- **形式**: VS Code Agent Plugin（Claude Plugin Format 互換）
- **目的**: GitHub Enterprise の管理・運用タスクを支援するスキル群を提供
- **バージョン**: `0.1.0`（初期開発段階）

## ディレクトリ構造

```
.claude-plugin/
  plugin.json            # プラグインメタデータ（name, description, version）
skills/
  <skill-name>/
    SKILL.md             # スキル定義（必須）
    *.sh, *.ps1, ...     # 補助スクリプト（任意）
    examples/            # サンプル・テンプレート（任意）
agents/                  # カスタムエージェント（.agent.md）
hooks/
  hooks.json             # Hook 設定
  scripts/               # Hook スクリプト
.mcp.json                # MCP サーバー定義
```

> 現在 `skills/` のみ存在。`agents/`, `hooks/`, `.mcp.json` は必要に応じて追加する。

## スキルの追加方法

### 1. ディレクトリ作成

`skills/<skill-name>/` ディレクトリを作成する。ディレクトリ名は SKILL.md の `name` フィールドと一致させること。

### 2. SKILL.md の作成

```markdown
---
name: <skill-name>
description: <スキルの説明。何ができるか・いつ使うかを具体的に書く。最大1024文字>
argument-hint: <スラッシュコマンド入力時のヒント（任意）>
user-invocable: true          # /メニューに表示するか（デフォルト: true）
disable-model-invocation: false  # モデル自動呼び出しを無効にするか（デフォルト: false）
---

# スキル名

詳細な手順・ガイドライン・例をここに記述する。
```

### 命名規則

- `name`: 小文字、ハイフン区切り（例: `manage-org-members`）、最大64文字
- ディレクトリ名と `name` は完全一致必須
- スクリプト参照は相対パスの Markdown リンクで記述: `[script](./run.sh)`

### スキル設計のガイドライン

- **1スキル1責務**: 1つの明確なタスクに焦点を当てる
- **説明は具体的に**: description でユースケースと能力を明示する（モデルの自動マッチングに影響）
- **参照ファイルはリンクする**: SKILL.md 内で参照しないファイルはロードされない
- **スクリプト内でのパス参照**: `${CLAUDE_PLUGIN_ROOT}` トークンを使用（プラグインはワークスペース外にインストールされるため相対パス不可）

## エージェントの追加方法

`agents/<agent-name>.agent.md` にエージェント定義を配置する。
詳細: [Custom Agents](https://code.visualstudio.com/docs/copilot/customization/custom-agents)

## Hook の追加方法

`hooks/hooks.json` に定義を配置する（Claude Format）。

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "type": "command",
        "command": "${CLAUDE_PLUGIN_ROOT}/hooks/scripts/example.sh"
      }
    ]
  }
}
```

対応イベント: `SessionStart`, `UserPromptSubmit`, `PreToolUse`, `PostToolUse`, `PreCompact`, `SubagentStart`, `SubagentStop`, `Stop`

## MCP サーバーの追加方法

ルート直下の `.mcp.json` に定義する。キーは `mcpServers`（`servers` ではない）。

```json
{
  "mcpServers": {
    "server-name": {
      "command": "${CLAUDE_PLUGIN_ROOT}/servers/server-bin",
      "args": ["--config", "${CLAUDE_PLUGIN_ROOT}/config.json"]
    }
  }
}
```

## 開発・テスト

### ローカルでの動作確認

プラグイン全体のテストとスキル単体のテストで方法が異なる。

#### プラグインとして登録（ユーザー設定）

`chat.pluginLocations` はユーザープロファイル設定のみ対応。VS Code の **ユーザー** `settings.json` に追加する:

```json
{
  "chat.pluginLocations": {
    "/path/to/github-enterprise-ops-plugin": true
  }
}
```

> ⚠️ ワークスペース設定（`.vscode/settings.json`）では使えない。

#### スキル単体のテスト（ワークスペース設定）

`chat.agentSkillsLocations` でスキルディレクトリを指定する（`.vscode/settings.json` で可）:

```json
{
  "chat.agentSkillsLocations": {
    "skills": true
  }
}
```

この方法は SKILL.md の内容のみテストできる。Hook・MCP・plugin.json は読み込まれない。

### スキルの確認

1. VS Code で `Chat: Configure Skills` を開く
2. プラグインのスキルが一覧に表示されることを確認
3. `/skill-name` でスラッシュコマンドとして呼び出せることを確認

## Git コミット規約

[Conventional Commits](https://www.conventionalcommits.org/) に従う。

```
type(scope): description

body (optional)
```

**type**: `feat`, `fix`, `docs`, `chore`, `refactor`
**scope**: `skills/<name>`, `agents`, `hooks`, `mcp`, `plugin` など

例:
- `feat(skills/manage-org): add organization member management skill`
- `docs(readme): update installation instructions`

## リファレンス

- [Agent Plugins](https://code.visualstudio.com/docs/copilot/customization/agent-plugins)
- [Agent Skills](https://code.visualstudio.com/docs/copilot/customization/agent-skills)
- [Agent Skills Specification](https://agentskills.io/)
- [Custom Agents](https://code.visualstudio.com/docs/copilot/customization/custom-agents)
- [Hooks](https://code.visualstudio.com/docs/copilot/customization/hooks)
- [MCP Servers](https://code.visualstudio.com/docs/copilot/customization/mcp-servers)
