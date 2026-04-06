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

| ページ | パス | 説明 | Reference |
|--------|------|------|-----------|
| Overview | `/enterprises/{enterprise}` | Enterprise README の表示・編集、外部リソースへのリンク集 | [詳細](./references/enterprise-overview.md) |
| Organizations | `/enterprises/{enterprise}/organizations` | Org 一覧管理・検索・フィルタ、カスタムプロパティの定義・設定 | [詳細](./references/enterprise-organizations.md) |
| People | `/enterprises/{enterprise}/people` | メンバー・管理者・外部コラボレーターの管理、カスタムロールの作成・割り当て | [詳細](./references/enterprise-people.md) |
| Identity provider | `/enterprises/{enterprise}/settings/single_sign_on_configuration` | IdP 連携設定（OIDC/SAML SSO）と IdP グループの管理 | [詳細](./references/enterprise-identity-provider.md) |
| AI Controls | `/enterprises/{enterprise}/ai-controls/agents` | AI 関連設定（Agents・Copilot ポリシー・MCP サーバー） | [詳細](./references/enterprise-ai-controls.md) |
| Policies | `/enterprises/{enterprise}/settings/policies/repositories` | ポリシー設定（リポジトリ操作、メンバー権限、Actions、セキュリティ等を Org に強制） | [詳細](./references/enterprise-policies.md) |
| GitHub Connect | `/enterprises/{enterprise}/enterprise_installations` | GHES と GHEC の接続状況確認 | [詳細](./references/enterprise-github-connect.md) |
| Security and quality | `/enterprises/{enterprise}/security/overview` | セキュリティアラートトレンド、リスク分析、カバレッジ、アラート一覧、バイパスリクエスト管理 | [詳細](./references/enterprise-security.md) |
| Billing and licensing | `/enterprises/{enterprise}/billing` | 課金・ライセンス管理、メータード使用量、プレミアムリクエスト分析 | [詳細](./references/enterprise-billing.md) |
| Compliance | `/enterprises/{enterprise}/settings/compliance` | コンプライアンスレポートのダウンロード、Dormant Users レポートの生成 | [詳細](./references/enterprise-compliance.md) |
| Insights | `/enterprises/{enterprise}/insights/copilot` | Copilot 利用状況・コード生成メトリクス、Actions 使用量・パフォーマンスメトリクス | [詳細](./references/enterprise-insights.md) |
| Settings | `/enterprises/{enterprise}/settings/profile` | 一般設定、認証、セキュリティ機能、ドメイン管理、Audit ログ、Webhook、ネットワーク構成 | [詳細](./references/enterprise-settings.md) |

### Organization レベル

ベースパス: `/{org}`

| ページ | パス | 説明 | Reference |
|--------|------|------|-----------|
| Overview | `/{org}` | Org トップページ、Pinned repos、リポジトリ一覧 | |
| Repositories | `/orgs/{org}/repositories` | リポジトリ一覧・検索・フィルタ | |
| Projects | `/orgs/{org}/projects` | プロジェクト一覧 | |
| Packages | `/orgs/{org}/packages` | パッケージ一覧 | |
| Teams | `/orgs/{org}/teams` | チーム一覧・管理 | |
| People | `/orgs/{org}/people` | メンバー一覧・管理 | |
| Security and quality | `/orgs/{org}/security/overview` | セキュリティアラートの検出・修復・予防、リスク評価、カバレッジ、Findings 管理 | [詳細](./references/org-security.md) |
| Insights | `/orgs/{org}/insights` | Copilot 利用状況・コード生成、Actions メトリクス、REST API 利用状況 | [詳細](./references/org-insights.md) |
| Settings | `/organizations/{org}/settings/profile` | Org の全般設定（プロフィール、ポリシー、アクセス管理、コード・自動化、セキュリティ等） | [詳細](./references/org-settings.md) |

### Repository レベル

ベースパス: `/{owner}/{repo}`

| ページ | パス | 説明 | Reference |
|--------|------|------|-----------|
| Code | `/{owner}/{repo}` | ソースコード・ブランチ・コミット | |
| Issues | `/{owner}/{repo}/issues` | Issue 一覧・管理 | |
| Pull requests | `/{owner}/{repo}/pulls` | PR 一覧・管理 | |
| Agents | `/{owner}/{repo}/agents` | エージェント一覧 | |
| Actions | `/{owner}/{repo}/actions` | CI/CD ワークフロー | |
| Projects | `/{owner}/{repo}/projects` | プロジェクト一覧 | |
| Wiki | `/{owner}/{repo}/wiki` | Wiki ページ | |
| Security and quality | `/{owner}/{repo}/security` | セキュリティアラート・脆弱性管理 | |
| Insights | `/{owner}/{repo}/pulse` | リポジトリ分析・トラフィック | |
| Settings | `/{owner}/{repo}/settings` | リポジトリの全般設定（ブランチ、アクセス、コード・自動化、セキュリティ、連携等） | [詳細](./references/repo-settings.md) |

## ナビゲーション構造

各ページの詳細なナビゲーション構造・設定項目は references/ 配下にトップナビ項目ごとに記録する。
ファイル名はプレフィックスでレベルを示す: `enterprise-*`, `org-*`, `repo-*`。
上記 URL パターンテーブルの Reference 列からリンクされている。
