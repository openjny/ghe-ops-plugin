# Enterprise People

> パス: `/enterprises/{enterprise}/people`

## 概要

Enterprise に所属する人（メンバー、管理者、外部コラボレーター等）の管理。ロール別の人数、ライセンス消費状況の確認が可能。

## サイドナビゲーション

| 項目 | パス |
|------|------|
| Members | `/enterprises/{enterprise}/people` |
| Administrators | `/enterprises/{enterprise}/admins` |
| Enterprise teams | `/enterprises/{enterprise}/teams` |
| Repository collaborators | `/enterprises/{enterprise}/outside_collaborators` |
| Enterprise roles | (展開可能なサブメニュー) |
| Organization roles | `/enterprises/{enterprise}/org_roles` |
| Suspended | `/enterprises/{enterprise}/suspended_members` |

## セクション: Members

> パス: `/enterprises/{enterprise}/people`

Enterprise メンバーの一覧と管理。

- Roles サマリー: Organization members, Organization owners, Enterprise owners, Billing managers, Guest collaborators, Unaffiliated の人数表示。各項目はクエリパラメータ `?query=role:{role}` でフィルタ可能
- User licenses consumed: ユーザー数と合計消費ライセンス数
- メンバー一覧: 名前、Org 所属数、2FA 状態、ライセンス状態
- 検索: 「Find a member…」
- フィルタ: Role, Organization, Two-factor authentication
- CSV report ダウンロード

## セクション: Administrators

> パス: `/enterprises/{enterprise}/admins`

Enterprise の管理者一覧。[^1]

## セクション: Enterprise teams

> パス: `/enterprises/{enterprise}/teams`

Enterprise 全体で横断的に使えるチーム。[^2]

## セクション: Repository collaborators

> パス: `/enterprises/{enterprise}/outside_collaborators`

Org メンバーではないが、特定リポジトリへのアクセス権を持つ外部コラボレーター。

## セクション: Enterprise roles

(展開可能なサブメニュー)

カスタム Enterprise ロールの管理。[^3]

## セクション: Organization roles

> パス: `/enterprises/{enterprise}/org_roles`

Org レベルのカスタムロールの管理。

## セクション: Suspended

> パス: `/enterprises/{enterprise}/suspended_members`

一時停止されたメンバーの一覧。

---

[^1]: [GitHub Docs: Viewing people in your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-users-in-your-enterprise/viewing-people-in-your-enterprise)
[^2]: [GitHub Docs: Managing enterprise teams](https://docs.github.com/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-users-in-your-enterprise/managing-enterprise-teams)
[^3]: [GitHub Docs: Managing custom roles for an enterprise](https://docs.github.com/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-users-in-your-enterprise/managing-support-entitlements-for-your-enterprise)
