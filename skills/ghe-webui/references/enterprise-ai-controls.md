# Enterprise AI Controls

> パス: `/enterprises/{enterprise}/ai-controls/agents`

Enterprise レベルの AI 関連設定。Agents（クラウドエージェント・パートナーエージェント・カスタムエージェント・トラッキングとガバナンス）、Copilot ポリシー（プライバシー・機能・課金・メトリクス・クライアント）、MCP サーバーの制御を行う。[^1]

## ナビゲーション

| 項目 | パス |
|------|------|
| Agents | `/enterprises/{enterprise}/ai-controls/agents` |
| Copilot | `/enterprises/{enterprise}/ai-controls/copilot` |
| MCP | `/enterprises/{enterprise}/ai-controls/mcp` |

## Agents

> パス: `/enterprises/{enterprise}/ai-controls/agents`

### Agent sessions

過去24時間のエージェントセッション履歴。

### Available Agents

#### GitHub 提供

| エージェント | 説明 |
|-------------|------|
| Copilot Cloud Agent | クラウドベースのコーディングエージェント |
| Copilot Code Review | PR のコードレビュー支援 |

各エージェントに Enabled/Disabled トグル。ポリシー設定リンク: `ai-controls/agents/policies`

#### Partner Agents (Preview)

| エージェント | 説明 |
|-------------|------|
| Anthropic Claude | Claude エージェント。Copilot 経由の Anthropic モデルや VS Code 上の Claude サードパーティエージェントとは別制御[^2] |
| OpenAI Codex | Codex エージェント。Copilot 経由の OpenAI モデルや VS Code 上の Codex サードパーティエージェントとは別制御 |

各エージェントに Enabled/Disabled トグル。Org に install が必要。

#### Custom Agents

Organization の設定ファイルを選択し、カスタムエージェントを Enterprise 全ユーザーに公開する。カスタムエージェントは MCP サーバーを定義可能。[^6]

### Tracking and governance

- **Only enterprise admins can edit agent files** — エージェントファイルの編集を Enterprise 管理者のみに制限する Ruleset。全リポジトリ対象のプッシュルール
- **Audit logs** — Enterprise 全体のエージェントアクティビティと変更の監査ログ（`actor:Copilot` でフィルタ）

## Copilot

> パス: `/enterprises/{enterprise}/ai-controls/copilot`

### Access management

> リンク先: `/enterprises/{enterprise}/enterprise_licensing/copilot`

Org へのアクセス付与、ユーザー・Enterprise team への直接ライセンス割り当て。

### Content exclusion

> パス: `/enterprises/{enterprise}/ai-controls/copilot/content-exclusion`

Copilot が読み取る対象から特定ファイル・リポジトリを除外する設定。[^3]

### Configure allowed models

> パス: `/enterprises/{enterprise}/ai-controls/copilot/models`

利用可能な AI モデルの選択。

### Privacy

- **Suggestions matching public code** — パブリックコードと一致する提案の許可/ブロック。ポリシー: Allowed / Blocked

### Features

- **Policies for enterprise-assigned users** — Enterprise 直接割り当てユーザーへの全機能ポリシー。ポリシー: Enabled everywhere / Disabled / Let organizations decide
- **Editor preview features** — エディタのプレビュー機能。ポリシー: Select a policy
- **Copilot can search the web** — Bing 経由の Web 検索。ポリシー: Enabled everywhere / Disabled / Let organizations decide
- **Copilot can search the web using model native search** — モデルのビルトイン検索 (Preview)。ポリシー: Select a policy
- **Copilot-generated commit messages** — GitHub.com 上のコミットメッセージ生成。ポリシー: Select a policy
- **Copilot Spaces** — Copilot Spaces の利用。ポリシー: Select a policy
- **Copilot Spaces Individual Access** — 個人所有の Copilot Spaces 作成。ポリシー: Select a policy
- **Copilot Spaces Individual Sharing** — 個人所有の Copilot Spaces 共有。ポリシー: Select a policy
- **Copilot Memory (Preview)** — リポジトリコンテキストの記憶[^4]。ポリシー: Select a policy
- **Enable custom models (Preview)** — API キーによるカスタムモデル利用。ポリシー: Enabled / Disabled

### Billing

- **Premium request paid usage** — プレミアムリクエストの有料利用。ポリシー: Enabled / Disabled

バジェット設定リンク: `/enterprises/{enterprise}/billing/budgets`

### Metrics

- **Copilot usage metrics (DPA-covered)** — ダッシュボードと API での利用メトリクス。ポリシー: Select a policy

### Copilot Clients

- **Copilot in GitHub.com** — GitHub.com 上の Copilot Chat とナレッジベース検索。ポリシー: Enabled everywhere / Disabled / Let organizations decide
- **Opt in to free text user feedback collection** — github.com でのフリーテキストフィードバック収集。ポリシー: On / Off トグル
- **Opt in for access to Copilot preview features** — github.com のプレビュー機能へのアクセス。ポリシー: On / Off トグル
- **Copilot CLI (DPA-covered)** — ターミナルでの Copilot 支援。ポリシー: Enabled everywhere / Disabled / Let organizations decide
- **Copilot in GitHub Desktop** — GitHub Desktop での Copilot 支援。ポリシー: Enabled everywhere / Disabled / Let organizations decide
- **Copilot Chat in the IDE** — コードエディタでの Copilot Chat。ポリシー: Enabled everywhere / Disabled / Let organizations decide
- **Copilot Chat in GitHub Mobile** — GitHub Mobile での Copilot Chat。ポリシー: Enabled everywhere / Disabled / Let organizations decide
- **Copilot Agent Mode in IDE Chat** — IDE での Agent Mode。ポリシー: Enabled everywhere / Disabled / Let organizations decide

## MCP

> パス: `/enterprises/{enterprise}/ai-controls/mcp`

- **MCP servers in Copilot** — すべての Copilot エディタと Coding Agent での MCP サーバー利用[^7][^8]。ポリシー: Enabled everywhere / Disabled / Let organizations decide
- **MCP Registry URL (Preview)** — 仕様準拠の MCP レジストリ URL を指定。レジストリに登録されたサーバーがサポート対象のエディタで表示される[^5][^9]。入力: テキスト入力 + Save/Clear
- **Restrict MCP access to registry servers (Preview)** — レジストリ設定に基づく MCP サーバーアクセス制御[^5]。ポリシー: Allow all / Registry only（レジストリ URL 設定時のみ有効）

[^1]: [GitHub Docs: Managing GitHub Copilot in your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/managing-github-copilot-in-your-enterprise)
[^2]: [GitHub Docs: About third-party agents](https://docs.github.com/en/copilot/concepts/agents/about-third-party-agents)
[^3]: [GitHub Docs: Excluding content from GitHub Copilot](https://docs.github.com/en/copilot/managing-copilot/managing-github-copilot-in-your-organization/setting-policies-for-copilot-in-your-organization/excluding-content-from-github-copilot)
[^4]: [GitHub Docs: Copilot Memory](https://docs.github.com/copilot/concepts/agents/copilot-memory)
[^5]: [GitHub Docs: Configure MCP server access](https://docs.github.com/en/copilot/how-tos/administer-copilot/manage-mcp-usage/configure-mcp-server-access)
[^6]: [GitHub Docs: About custom agents](https://docs.github.com/en/copilot/concepts/agents/coding-agent/about-custom-agents)
[^7]: [GitHub Docs: Extending Copilot Chat with MCP](https://docs.github.com/en/copilot/customizing-copilot/extending-copilot-chat-with-mcp)
[^8]: [GitHub Docs: Extending Copilot Coding Agent with MCP](https://docs.github.com/en/copilot/customizing-copilot/extending-copilot-coding-agent-with-mcp)
[^9]: [MCP Registry Specification](https://github.com/modelcontextprotocol/registry)
