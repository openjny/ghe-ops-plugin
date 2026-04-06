# Enterprise People

> パス: `/enterprises/{enterprise}/people`

## 概要

Enterprise に所属する人（メンバー、管理者、外部コラボレーター等）の管理。ロール別の人数、ライセンス消費状況の確認、カスタムロールの作成・割り当てが可能。[^1]

## ナビゲーション

| 項目 | パス |
|------|------|
| Members | `/enterprises/{enterprise}/people` |
| Administrators | `/enterprises/{enterprise}/admins` |
| Enterprise teams | `/enterprises/{enterprise}/teams` |
| Repository collaborators | `/enterprises/{enterprise}/outside_collaborators` |
| Enterprise roles > Role management | `/enterprises/{enterprise}/enterprise_roles` |
| Enterprise roles > Role assignments | `/enterprises/{enterprise}/enterprise_role_assignments` |
| Organization roles | `/enterprises/{enterprise}/org_roles` |
| Suspended | `/enterprises/{enterprise}/suspended_members` |

## Members

> パス: `/enterprises/{enterprise}/people`

Enterprise メンバーの一覧と管理。

- Roles サマリー: Organization members, Organization owners, Enterprise owners, Billing managers, Guest collaborators, Unaffiliated の人数表示。各項目はクエリパラメータ `?query=role:{role}` でフィルタ可能 [^2]
- User licenses consumed: By users（ユーザー数）と Total consumed（合計消費ライセンス数）
- メンバー一覧: 名前、Org 所属数、2FA 状態、ライセンス状態
- 検索: 「Find a member…」
- フィルタ: Role, Organization, Two-factor authentication
- ソート: Sort ボタン
- CSV report ダウンロード
- メンバー選択チェックボックスによる一括操作

## Administrators

> パス: `/enterprises/{enterprise}/admins`

Enterprise の管理者（Enterprise owners、Billing managers）の一覧と管理。[^1]

- 検索: 「Find an administrator…」
- フィルタ: Role, Organization, Two-factor authentication
- 管理者一覧: 名前、Org 所属数、2FA 状態、ロール（Owner 等）
- 各管理者のアクションメニュー（Administrator menu）

## Enterprise teams

> パス: `/enterprises/{enterprise}/teams`

Enterprise 全体で横断的に使えるチーム。[^3]

- Preview 機能
- 「Create Enterprise team」ボタン: 新しい Enterprise team を作成
- 検索: 「Find a team...」
- チーム一覧: チーム名、メンバー数、アクションメニュー
- ソート: Name
- 表示密度切替: Comfortable / Compact

## Repository collaborators

> パス: `/enterprises/{enterprise}/outside_collaborators`

Org メンバーではないが、特定リポジトリへのアクセス権を持つ外部コラボレーター（repository collaborator）。[^1]

- 検索: 「Find a collaborator…」
- フィルタ: Organization, Visibility, Two-factor authentication

## Enterprise roles

### Role management

> パス: `/enterprises/{enterprise}/enterprise_roles`

Enterprise カスタムロールの作成・管理。Enterprise ロールはユーザーや Enterprise team に Enterprise 設定の特定部分へのアクセスを付与する。[^4]

- Preview 機能
- Custom enterprise roles: 最大 20 個のカスタムロールを作成可能
  - 「Create custom role」ボタン（`/enterprises/{enterprise}/enterprise_roles/new`）
- Pre-defined roles:
  - Enterprise App Manager: Enterprise が所有するインテグレーションの管理権限
  - Enterprise Security Manager: 全 Organization へのアクセスと、Enterprise および全 Organization のセキュリティポリシー・アラート・設定の管理権限
- 各ロールの「Show role permissions」ボタンで権限詳細を確認可能

### Role assignments

> パス: `/enterprises/{enterprise}/enterprise_role_assignments`

Enterprise ロールのユーザー・チームへの割り当て管理。[^4]

- Preview 機能
- 「Assign role」ボタン（`/enterprises/{enterprise}/enterprise_role_assignments/new`）
- 割り当て済みユーザー・チームの一覧

## Organization roles

> パス: `/enterprises/{enterprise}/org_roles`

Enterprise レベルでの Organization カスタムロールの作成・管理。Organization ロールは Organization 設定およびリポジトリ設定へのアクセスを付与する。リポジトリ権限は Organization 内の全リポジトリに適用される。[^5]

- Custom organization roles: 最大 20 個のカスタムロールを Enterprise レベルで作成可能
  - 「Create custom role」ボタン（`/enterprises/{enterprise}/org_roles/new`）
- Pre-defined roles:
  - All-repository read: Organization 内の全リポジトリへの読み取りアクセス
  - All-repository write: Organization 内の全リポジトリへの書き込みアクセス
  - All-repository triage: Organization 内の全リポジトリへのトリアージアクセス
  - All-repository maintain: Organization 内の全リポジトリへのメンテナンスアクセス
  - All-repository admin: Organization 内の全リポジトリへの管理者アクセス
  - Apps manager: Organization が所有する全 GitHub App の管理権限
  - CI/CD Admin: Organization の Actions ポリシー、ランナー、ランナーグループ、ネットワーク構成、シークレット、変数、使用状況メトリクスの管理者アクセス
  - Security manager: Organization およびその全リポジトリのセキュリティポリシー・アラート・設定の管理権限
- 各ロールの「Show role permissions」ボタンで権限詳細を確認可能

## Suspended

> パス: `/enterprises/{enterprise}/suspended_members`

一時停止されたメンバーの一覧。Enterprise Managed Users を使用している場合、IdP でプロビジョニング解除されたユーザーが表示される。[^1]

- 検索: 「Find a suspended member…」

---

[^1]: [GitHub Docs: Viewing people in your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-users-in-your-enterprise/viewing-people-in-your-enterprise)
[^2]: [GitHub Docs: Roles in an enterprise](https://docs.github.com/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-roles-in-your-enterprise/abilities-of-roles)
[^3]: [GitHub Docs: Teams in an enterprise](https://docs.github.com/enterprise-cloud@latest/admin/concepts/enterprise-fundamentals/teams-in-an-enterprise)
[^4]: [GitHub Docs: Creating custom roles in an enterprise](https://docs.github.com/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-roles-in-your-enterprise/create-custom-roles)
[^5]: [GitHub Docs: Permissions of custom organization roles](https://docs.github.com/enterprise-cloud@latest/organizations/managing-peoples-access-to-your-organization-with-roles/about-custom-organization-roles)
