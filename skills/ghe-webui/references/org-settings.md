# Organization Settings

> パス: `/organizations/{org}/settings/profile`

## 概要

Organization の全般設定。プロフィール、ポリシー、アクセス管理、コード・プランニング・自動化、セキュリティ、サードパーティアクセス、インテグレーション等を管理する。

## Org トップナビゲーション

Org のすべてのページで共通のトップナビゲーション。

| 項目 | パス |
|------|------|
| Repositories | `/{org}` |
| Projects | `/orgs/{org}/projects` |
| Packages | `/orgs/{org}/packages` |
| Teams | `/orgs/{org}/teams` |
| People | `/orgs/{org}/people` |
| Security and quality | `/orgs/{org}/security/overview` |
| Insights | `/orgs/{org}/insights` |
| Settings | `/organizations/{org}/settings/profile` |

## Settings サイドナビゲーション

### General

- Org のプロフィール情報（表示名、メール、説明、URL、所在地）の設定
- README の設定
- Discussions の有効化設定

### Policies

(展開可能なサブメニュー)

### Access

| 項目 | パス |
|------|------|
| Billing and plans | `/organizations/{org}/settings/billing/summary` |
| Organization roles | (展開可能なサブメニュー) |
| Repository roles | `/organizations/{org}/settings/roles` |
| Member privileges | `/organizations/{org}/settings/member_privileges` |
| Import/Export | `/organizations/{org}/settings/import-export` |
| Moderation | (展開可能なサブメニュー) |

### Code, planning, and automation

| 項目 | パス |
|------|------|
| Repository | (展開可能なサブメニュー) |
| Codespaces | (展開可能なサブメニュー) |
| Planning | (展開可能なサブメニュー) |
| Copilot | (展開可能なサブメニュー) |
| Actions | (展開可能なサブメニュー) |
| Webhooks | `/organizations/{org}/settings/hooks` |
| Discussions | `/organizations/{org}/settings/discussions` |
| Packages | `/organizations/{org}/settings/packages` |
| Hosted compute networking | `/organizations/{org}/settings/network_configurations` |
| Custom properties | `/organizations/{org}/settings/org-custom-properties` |

### Security

| 項目 | パス |
|------|------|
| Authentication security | `/organizations/{org}/settings/security` |
| Advanced Security | (展開可能なサブメニュー) |
| Deploy keys | `/organizations/{org}/settings/deploy_keys` |
| Compliance | `/organizations/{org}/settings/compliance` |
| Verified and approved domains | `/organizations/{org}/settings/domains` |
| Secrets and variables | (展開可能なサブメニュー) |

### Third-party Access

| 項目 | パス |
|------|------|
| GitHub Apps | `/organizations/{org}/settings/installations` |
| OAuth app policy | `/organizations/{org}/settings/oauth_application_policy` |
| Personal access tokens | (展開可能なサブメニュー) |

### Integrations

| 項目 | パス |
|------|------|
| Scheduled reminders | `/organizations/{org}/settings/reminders` |

### Messages

| 項目 | パス |
|------|------|
| Announcement | `/organizations/{org}/settings/announcement` |

### Archive

| 項目 | パス |
|------|------|
| Logs | (展開可能なサブメニュー) |
| Deleted repositories | `/organizations/{org}/settings/deleted_repositories` |

### Developer settings

(展開可能なサブメニュー)

---

[^1]: [GitHub Docs: Managing your organization's settings](https://docs.github.com/enterprise-cloud@latest/organizations/managing-organization-settings)
