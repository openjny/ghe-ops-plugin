# Repository Settings

> パス: `/{owner}/{repo}/settings`

## 概要

リポジトリの全般設定。リポジトリ名、デフォルトブランチ、アクセス管理、コード・自動化、セキュリティ、インテグレーション等を管理する。

## Repo トップナビゲーション

リポジトリのすべてのページで共通のトップナビゲーション。

| 項目 | パス |
|------|------|
| Code | `/{owner}/{repo}` |
| Issues | `/{owner}/{repo}/issues` |
| Pull requests | `/{owner}/{repo}/pulls` |
| Discussions | `/{owner}/{repo}/discussions` |
| Agents | `/{owner}/{repo}/agents` |
| Actions | `/{owner}/{repo}/actions` |
| Projects | `/{owner}/{repo}/projects` |
| Wiki | `/{owner}/{repo}/wiki` |
| Security and quality | `/{owner}/{repo}/security` |
| Insights | `/{owner}/{repo}/pulse` |
| Settings | `/{owner}/{repo}/settings` |

## Settings サイドナビゲーション

### General

- リポジトリ名の変更
- テンプレートリポジトリの設定
- デフォルトブランチの変更
- リリースの不変性設定
- Social preview 画像の設定
- Features の有効/無効（Wikis, Issues, Sponsorships, Discussions, Projects 等）
- Pull Requests のマージ戦略設定（merge commit, squash, rebase）
- 自動マージ、自動ブランチ削除の設定
- Danger Zone: リポジトリの可視性変更、アーカイブ、転送、削除

### Access

| 項目 | パス |
|------|------|
| Collaborators and teams | `/{owner}/{repo}/settings/access` |
| Team and member roles | `/{owner}/{repo}/settings/role_details` |

### Code and automation

| 項目 | パス |
|------|------|
| Branches | `/{owner}/{repo}/settings/branches` |
| Tags | `/{owner}/{repo}/settings/tag_protection` |
| Rules | (展開可能なサブメニュー) |
| Actions | (展開可能なサブメニュー) |
| Webhooks | `/{owner}/{repo}/settings/hooks` |
| Copilot | (展開可能なサブメニュー) |
| Environments | `/{owner}/{repo}/settings/environments` |
| Pages | `/{owner}/{repo}/settings/pages` |
| Custom properties | `/{owner}/{repo}/settings/custom-properties` |

### Security and quality

| 項目 | パス |
|------|------|
| Advanced Security | `/{owner}/{repo}/settings/security_analysis` |
| Code quality | `/{owner}/{repo}/settings/code-quality` |
| Deploy keys | `/{owner}/{repo}/settings/keys` |
| Secrets and variables | (展開可能なサブメニュー) |

### Integrations

| 項目 | パス |
|------|------|
| GitHub Apps | `/{owner}/{repo}/settings/installations` |
| Email notifications | `/{owner}/{repo}/settings/notifications` |
| Autolink references | `/{owner}/{repo}/settings/key_links` |

---

[^1]: [GitHub Docs: Managing repository settings](https://docs.github.com/enterprise-cloud@latest/repositories/managing-your-repositorys-settings-and-features)
