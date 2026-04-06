---
name: ghe-webui
description: "GitHub Enterprise の Web UI 構造・URL パターン・ナビゲーション・各ページの設定項目を記録した知識ベース。Use when: GHE の設定がどこにあるか知りたい、URL パターンを調べたい、Enterprise/Org/Repo の管理画面の構造を把握したい。Triggers: GHE UI, 設定場所, URL パターン, ナビゲーション, 管理画面構造, Enterprise 設定, Org 設定, どこにある"
argument-hint: "調べたい設定やページ (例: Copilot 設定はどこ, AI Controls の構造)"
---

# GitHub Enterprise Web UI 知識ベース

GitHub Enterprise の Web UI のナビゲーション構造、URL パターン、各ページの設定項目を記録する。

> **注意**: GitHub の UI は頻繁に更新される。情報が古い可能性がある場合は、実際にブラウザで確認すること（`clickops` スキルを使用）。

## URL パターン

すべての URL は `https://{host}` をベースとする。`{host}` は GitHub Enterprise のホスト名（例: `github.com`、GHES のカスタムドメインなど）。

### Enterprise レベル

ベースパス: `/enterprises/{enterprise}`

| ページ | パス | 備考 |
|--------|------|------|
| Overview | `/enterprises/{enterprise}` | Enterprise README、リンク集 |
| Organizations | `/enterprises/{enterprise}/organizations` | Org 一覧、Custom Properties |
| People | `/enterprises/{enterprise}/people` | メンバー一覧 |
| Identity provider | `/enterprises/{enterprise}/settings/single_sign_on_configuration` | SSO 設定 |
| AI Controls | `/enterprises/{enterprise}/ai-controls/agents` | Agents, Copilot, MCP |
| Policies | `/enterprises/{enterprise}/settings/policies/repositories` | リポジトリ等のポリシー |
| GitHub Connect | `/enterprises/{enterprise}/enterprise_installations` | |
| Security and quality | `/enterprises/{enterprise}/security/overview` | セキュリティ概要・アラート |
| Billing and licensing | `/enterprises/{enterprise}/billing` | |
| Compliance | `/enterprises/{enterprise}/settings/compliance` | |
| Insights | `/enterprises/{enterprise}/insights/copilot` | Copilot 利用状況 |
| Settings | `/enterprises/{enterprise}/settings/profile` | Enterprise プロフィール |

### Organization レベル

| ページ | パス | 備考 |
|--------|------|------|
| Org トップ | `/{org}` | |
| People | `/orgs/{org}/people` | メンバー一覧 |
| Teams | `/orgs/{org}/teams` | チーム一覧 |
| Settings | `/organizations/{org}/settings/` | |
| Copilot | `/organizations/{org}/settings/copilot` | |
| Actions | `/organizations/{org}/settings/actions` | |
| Security | `/orgs/{org}/security` | セキュリティ概要 |
| Audit log | `/organizations/{org}/settings/audit-log` | |
| Rulesets | `/organizations/{org}/settings/rules` | |
| Custom properties | `/organizations/{org}/settings/custom-properties` | |
| Billing | `/organizations/{org}/settings/billing` | |

### Repository レベル

| ページ | パス | 備考 |
|--------|------|------|
| Settings | `/{owner}/{repo}/settings` | |

## ナビゲーション構造

各ページの詳細なナビゲーション構造・設定項目は references/ 配下にトップナビ項目ごとに記録する。
ファイル名はプレフィックスでレベルを示す: `enterprise-*`, `org-*`, `repo-*`。

### Enterprise レベル

- [Overview](./references/enterprise-overview.md)
- [Organizations](./references/enterprise-organizations.md)
- [People](./references/enterprise-people.md)
- [Identity provider](./references/enterprise-identity-provider.md)
- [AI Controls](./references/enterprise-ai-controls.md)
- [Policies](./references/enterprise-policies.md)
- [GitHub Connect](./references/enterprise-github-connect.md)
- [Security and quality](./references/enterprise-security.md)
- [Billing and licensing](./references/enterprise-billing.md)
- [Compliance](./references/enterprise-compliance.md)
- [Insights](./references/enterprise-insights.md)
- [Settings](./references/enterprise-settings.md)

### Organization レベル

- [Settings](./references/org-settings.md)

### Repository レベル

- [Settings](./references/repo-settings.md)
