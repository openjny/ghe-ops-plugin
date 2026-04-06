# Organization Settings

> パス: `/organizations/{org}/settings/profile`

## 概要

Organization の全般設定。プロフィール、ポリシー、アクセス管理、コード・プランニング・自動化、セキュリティ、サードパーティアクセス、インテグレーション等を管理する。

## ナビゲーション

| 項目 | パス |
|------|------|
| **General** | |
| Profile | `/organizations/{org}/settings/profile` |
| Policies > Repository | `/organizations/{org}/settings/policies/repositories` |
| **Access** | |
| Billing and plans | `/organizations/{org}/settings/billing/summary` |
| Organization roles > Role management | `/organizations/{org}/settings/org_roles` |
| Organization roles > Role assignments | `/organizations/{org}/settings/org_role_assignments` |
| Repository roles | `/organizations/{org}/settings/roles` |
| Member privileges | `/organizations/{org}/settings/member_privileges` |
| Import/Export | `/organizations/{org}/settings/import-export` |
| Moderation > Blocked users | `/organizations/{org}/settings/blocked_users` |
| Moderation > Interaction limits | `/organizations/{org}/settings/interaction_limits` |
| Moderation > Code review limits | `/organizations/{org}/settings/code_review_limits` |
| Moderation > Moderators | `/organizations/{org}/settings/moderators` |
| **Code, planning, and automation** | |
| Repository > General | `/organizations/{org}/settings/repository-defaults` |
| Repository > Topics | `/orgs/{org}/topics` |
| Repository > Rulesets | `/organizations/{org}/settings/rules` |
| Repository > Rule insights | `/organizations/{org}/settings/rules/insights` |
| Repository > Bypass requests | `/organizations/{org}/settings/rules/bypass_requests` |
| Repository > Custom properties | `/organizations/{org}/settings/custom-properties` |
| Codespaces > General | `/organizations/{org}/settings/codespaces` |
| Codespaces > Policies | `/organizations/{org}/settings/codespaces/policies` |
| Planning > Projects | `/organizations/{org}/settings/projects` |
| Planning > Issue types | `/organizations/{org}/settings/issue-types` |
| Copilot > Access | `/organizations/{org}/settings/copilot/seat_management` |
| Copilot > Policies | `/organizations/{org}/settings/copilot/policies` |
| Copilot > Models | `/organizations/{org}/settings/copilot/models` |
| Copilot > Custom instructions | `/organizations/{org}/settings/copilot/custom_instructions` |
| Copilot > Content exclusion | `/organizations/{org}/settings/copilot/content_exclusion` |
| Copilot > Cloud agent | `/organizations/{org}/settings/copilot/coding_agent` |
| Actions > General | `/organizations/{org}/settings/actions` |
| Actions > Runners | `/organizations/{org}/settings/actions/runners` |
| Actions > Runner groups | `/organizations/{org}/settings/actions/runner-groups` |
| Actions > Custom images | `/organizations/{org}/settings/actions/custom-images` |
| Actions > Caches | `/organizations/{org}/settings/actions/caches` |
| Actions > OIDC | `/organizations/{org}/settings/actions/oidc-configuration` |
| Webhooks | `/organizations/{org}/settings/hooks` |
| Discussions | `/organizations/{org}/settings/discussions` |
| Packages | `/organizations/{org}/settings/packages` |
| Hosted compute networking | `/organizations/{org}/settings/network_configurations` |
| Custom properties | `/organizations/{org}/settings/org-custom-properties` |
| **Security** | |
| Authentication security | `/organizations/{org}/settings/security` |
| Advanced Security > Configurations | `/organizations/{org}/settings/security_products` |
| Advanced Security > Global settings | `/organizations/{org}/settings/security_analysis` |
| Deploy keys | `/organizations/{org}/settings/deploy_keys` |
| Compliance | `/organizations/{org}/settings/compliance` |
| Verified and approved domains | `/organizations/{org}/settings/domains` |
| Secrets and variables > Actions | `/organizations/{org}/settings/secrets/actions` |
| Secrets and variables > Codespaces | `/organizations/{org}/settings/secrets/codespaces` |
| Secrets and variables > Dependabot | `/organizations/{org}/settings/secrets/dependabot` |
| Secrets and variables > Private registries | `/organizations/{org}/settings/secrets/private_registries` |
| **Third-party Access** | |
| GitHub Apps | `/organizations/{org}/settings/installations` |
| OAuth app policy | `/organizations/{org}/settings/oauth_application_policy` |
| Personal access tokens > Settings | `/organizations/{org}/settings/personal-access-tokens` |
| Personal access tokens > Active tokens | `/organizations/{org}/settings/personal-access-tokens/active` |
| Personal access tokens > Pending requests | `/organizations/{org}/settings/personal-access-token-requests` |
| **Integrations** | |
| Scheduled reminders | `/organizations/{org}/settings/reminders` |
| **Messages** | |
| Announcement | `/organizations/{org}/settings/announcement` |
| **Archive** | |
| Logs > Audit log | `/organizations/{org}/settings/audit-log` |
| Deleted repositories | `/organizations/{org}/settings/deleted_repositories` |
| **Developer settings** | |
| OAuth Apps | `/organizations/{org}/settings/applications` |
| GitHub Apps | `/organizations/{org}/settings/apps` |

## General

### Profile

> パス: `/organizations/{org}/settings/profile`

- Org のプロフィール情報（表示名、メール、説明、URL、所在地、ソーシャルアカウント）の設定
- プロフィール画像のアップロード
- Gravatar email の設定
- Member appearance: Profile name visibility（On / Off トグル）[^2]
- GitHub Developer Program への参加
- Terms of Service（Corporate / Standard）の表示
- Danger zone: Org の名前変更、アーカイブ、削除

### Policies > Repository

> パス: `/organizations/{org}/settings/policies/repositories`

- (Beta) Ruleset ベースでメンバーがリポジトリに対して実行できる操作（削除・転送等）を制限するポリシーを定義 [^3]

## Access

### Billing and plans

> パス: `/organizations/{org}/settings/billing/summary`

- Enterprise 管理の Org は Enterprise レベルで課金される旨を表示 [^4]

### Organization roles > Role management

> パス: `/organizations/{org}/settings/org_roles`

- カスタム Org ロールの作成・管理（最大 20 個）。Org 設定およびリポジトリ設定へのアクセス権を付与 [^5]

### Organization roles > Role assignments

> パス: `/organizations/{org}/settings/org_role_assignments`

- ユーザー・チームへの Org ロールの割り当て

### Repository roles

> パス: `/organizations/{org}/settings/roles`

- 事前定義ロール（Read / Triage / Write / Maintain / Admin）の確認、カスタムリポジトリロールの作成 [^6]

### Member privileges

> パス: `/organizations/{org}/settings/member_privileges`

- メンバーの基本権限と機能アクセスを設定 [^7]

| セクション | 設定項目 |
|-----------|---------|
| Base permissions | Org リポジトリへの基本権限（None / Read / Write / Admin） |
| Repository creation | リポジトリ作成権限（Private / Internal） |
| Repository forking | Private / Internal リポジトリのフォーク許可、フォーク先の制限（同一 Org / Enterprise 内 / ユーザーアカウント / Everywhere） |
| Repository collaborators | 外部コラボレーターの招待権限（Members and outside collaborators / Members only） |
| Repository discussions | Read 権限ユーザーによる Discussion 作成の許可 |
| Projects base permissions | Projects のデフォルトロール |
| Pages creation | GitHub Pages サイト作成の許可 [^11] |
| App access requests | GitHub / OAuth アプリのアクセスリクエストを許可するかの選択（Members / Disable） |
| GitHub Apps | リポジトリ管理者による GitHub Apps のインストール許可 |
| Repository visibility change | 管理者によるリポジトリ可視性変更の許可 |
| Repository deletion and transfer | 管理者によるプライベートリポジトリの削除・転送の許可 |
| Issue deletion | 管理者による Issue 削除の許可 [^12] |
| Team creation rules | メンバーによるチーム作成の許可 [^13] |
| Dependency insights | メンバーによる依存関係インサイトの閲覧許可 [^14] |

### Import/Export

> パス: `/organizations/{org}/settings/import-export`

- Mannequin（プレースホルダーアカウント）のインポート・エクスポート

### Moderation > Blocked users

> パス: `/organizations/{org}/settings/blocked_users`

- ユーザーをブロックしてリポジトリへのアクセスを拒否 [^8]

### Moderation > Interaction limits

> パス: `/organizations/{org}/settings/interaction_limits`

- 外部ユーザーのインタラクション（コメント、Issue 作成、PR 作成）を一時的に制限 [^9]

### Moderation > Code review limits

> パス: `/organizations/{org}/settings/code_review_limits`

- パブリックリポジトリの PR でのレビュー（approve / request changes）を制限 [^10]

### Moderation > Moderators

> パス: `/organizations/{org}/settings/moderators`

- モデレーター（最大 10 名のメンバーまたはチーム）の追加。モデレーターはユーザーのブロック・コメントの最小化・インタラクション制限の管理が可能

## Code, planning, and automation

### Repository > General

> パス: `/organizations/{org}/settings/repository-defaults`

- デフォルトブランチ名、コミットサインオフ要件、リリースの不変性（Immutable releases）、デフォルトラベルの管理 [^15]

### Repository > Topics

> パス: `/orgs/{org}/topics`

- Org 内リポジトリのトピック管理

### Repository > Rulesets

> パス: `/organizations/{org}/settings/rules`

- ブランチ・タグ保護、ステータスチェック、線形コミット履歴、フォースプッシュ制限等を定義するルールセットの作成・管理 [^16]

### Repository > Rule insights

> パス: `/organizations/{org}/settings/rules/insights`

- ルール評価結果の確認（evaluate モードでのテスト含む）

### Repository > Bypass requests

> パス: `/organizations/{org}/settings/rules/bypass_requests`

- ルールセットのバイパスリクエストの確認・承認

### Repository > Custom properties

> パス: `/organizations/{org}/settings/custom-properties`

- リポジトリに付与するカスタムプロパティ（コンプライアンスフレームワーク、データ機密度等）の定義 [^17]

### Codespaces > General

> パス: `/organizations/{org}/settings/codespaces`

- Codespaces アクセス制御（Disabled / 特定メンバー / 全メンバー / 外部コラボレーター含む）、コードスペース所有権（Organization / User）、アクセスとセキュリティ（Deprecated）の設定 [^18]

### Codespaces > Policies

> パス: `/organizations/{org}/settings/codespaces/policies`

- Codespaces のポリシー（マシンタイプ、ポート可視性等の制約）を作成。Org に課金されるコードスペースに適用

### Planning > Projects

> パス: `/organizations/{org}/settings/projects`

- Projects の有効化、メンバーによる可視性変更の許可、推奨テンプレートの設定 [^19]

### Planning > Issue types

> パス: `/organizations/{org}/settings/issue-types`

- Org 全体で使用する Issue タイプのカスタマイズ（最大 25 種類）

### Copilot > Access

> パス: `/organizations/{org}/settings/copilot/seat_management`

- GitHub Copilot Business のシート割り当てとコスト管理 [^20]

### Copilot > Policies

> パス: `/organizations/{org}/settings/copilot/policies`

- Copilot の機能別ポリシー設定 [^21]

| カテゴリ | ポリシー項目 |
|---------|------------|
| Billing | Premium request paid usage |
| Features | Copilot in GitHub.com / Chat in the IDE / Editor preview features / Agent Mode in IDE Chat / Chat in GitHub Mobile / CLI / GitHub Desktop / Web search (Preview) / Usage metrics / Code review |
| Duplicate Detection Filter | 重複コード検出フィルタ |
| Feedback | Opt in to free text user feedback collection |
| Preview | Opt in to preview features（GitHub.com / code review） |

### Copilot > Models

> パス: `/organizations/{org}/settings/copilot/models`

- デフォルトモデルとカスタムモデルの管理

### Copilot > Custom instructions

> パス: `/organizations/{org}/settings/copilot/custom_instructions`

- Copilot に適用するコーディング標準・言語・フレームワークの指示を定義

### Copilot > Content exclusion

> パス: `/organizations/{org}/settings/copilot/content_exclusion`

- Copilot がアクセス・利用できないリポジトリ・パスの指定 [^22]

### Copilot > Cloud agent

> パス: `/organizations/{org}/settings/copilot/coding_agent`

- Copilot cloud agent の設定

| セクション | 設定項目 |
|-----------|---------|
| Repository access | Copilot cloud agent を有効にするリポジトリの選択 |
| Internet access | ファイアウォールの有効化（推奨）、推奨 allowlist、リポジトリ独自ルール許可、Organization カスタム allowlist |
| Runner type | デフォルトランナータイプの選択、リポジトリによるランナータイプのカスタマイズ許可 |

### Actions > General

> パス: `/organizations/{org}/settings/actions`

- Actions の全般設定 [^23]

| セクション | 設定項目 |
|-----------|---------|
| General actions permissions | 許可するアクション（All / Enterprise only / Enterprise + select non-enterprise）、GitHub 作成アクション・Marketplace 検証済みアクション・SHA ピン留めの要件 |
| Runners | リポジトリレベルのセルフホストランナー作成の許可 |
| Custom images | カスタムイメージ保持期間のデフォルト設定 |
| Artifact and log retention | 成果物・ログの保持期間（Enterprise の上限に従う） |
| Cache | キャッシュの保持期間・サイズ上限の設定 |
| Fork pull request workflows | フォーク PR からのワークフロー実行許可、Write トークン・シークレットの送信、承認要件 |
| Workflow permissions | デフォルトの GITHUB_TOKEN 権限（Read and write / Read only）、PR 作成・承認の許可 |

### Actions > Runners

> パス: `/organizations/{org}/settings/actions/runners`

- セルフホストランナーの登録・管理

### Actions > Runner groups

> パス: `/organizations/{org}/settings/actions/runner-groups`

- ランナーグループの管理。リポジトリごとのランナーアクセス制御

### Actions > Custom images

> パス: `/organizations/{org}/settings/actions/custom-images`

- カスタムイメージとバージョンの管理

### Actions > Caches

> パス: `/organizations/{org}/settings/actions/caches`

- ワークフローキャッシュの閲覧・管理

### Actions > OIDC

> パス: `/organizations/{org}/settings/actions/oidc-configuration`

- OIDC トークンの subject claim カスタマイズ、カスタムプロパティの claims への追加

### Webhooks

> パス: `/organizations/{org}/settings/hooks`

- 外部サービスへのイベント通知用 Webhook の管理

### Discussions

> パス: `/organizations/{org}/settings/discussions`

- Org レベルの Discussions の有効化とソースリポジトリの選択 [^24]

### Packages

> パス: `/organizations/{org}/settings/packages`

- パッケージ作成権限（Private / Internal）の設定、削除済みパッケージの復元（30 日以内）

### Hosted compute networking

> パス: `/organizations/{org}/settings/network_configurations`

- GitHub ホステッドコンピューティングのネットワーク構成 [^25]

### Custom properties

> パス: `/organizations/{org}/settings/org-custom-properties`

- Organization 自体に付与するカスタムプロパティの定義

## Security

### Authentication security

> パス: `/organizations/{org}/settings/security`

- SSH 認証局の管理、IP 許可リストの有効化・設定（GitHub Apps 用自動設定含む） [^26]

### Advanced Security > Configurations

> パス: `/organizations/{org}/settings/security_products`

- Secret Protection・Code Security・Dependabot の構成管理

### Advanced Security > Global settings

> パス: `/organizations/{org}/settings/security_analysis`

- グローバル Advanced Security 設定 [^27]

| セクション | 設定項目 |
|-----------|---------|
| Dependabot | グループ化されたセキュリティアップデート、ランナータイプの選択（GitHub Actions runners）、カスタムラベル |
| Code scanning | Extended query suite の推奨、CodeQL 拡張分析の有効化、Copilot Autofix |
| Secret scanning | Push protection（コミットブロック時の CLI / Web UI リソースリンク）、カスタムパターン（最大 500 個） |
| Billing | Active committer 単位の課金情報（Private / Internal リポジトリ） |

### Deploy keys

> パス: `/organizations/{org}/settings/deploy_keys`

- Org 全体のデプロイキーの有効化 / 無効化 [^28]

### Compliance

> パス: `/organizations/{org}/settings/compliance`

- コンプライアンスレポートの閲覧

### Verified and approved domains

> パス: `/organizations/{org}/settings/domains`

- Org のドメイン検証・承認 [^29]

### Secrets and variables > Actions

> パス: `/organizations/{org}/settings/secrets/actions`

- Actions 用の暗号化シークレット・変数の管理。リポジトリアクセススコープの設定

### Secrets and variables > Codespaces

> パス: `/organizations/{org}/settings/secrets/codespaces`

- Codespaces 用の暗号化シークレットの管理

### Secrets and variables > Dependabot

> パス: `/organizations/{org}/settings/secrets/dependabot`

- Dependabot 用の認証情報の管理（フォークには渡されない）

### Secrets and variables > Private registries

> パス: `/organizations/{org}/settings/secrets/private_registries`

- CodeQL default setup / Dependabot 用のプライベートレジストリ構成（パスワード・トークンは暗号化シークレットとして管理）

## Third-party Access

### GitHub Apps

> パス: `/organizations/{org}/settings/installations`

- インストール済み GitHub Apps の管理、保留中のインストールリクエストの確認

### OAuth app policy

> パス: `/organizations/{org}/settings/oauth_application_policy`

- サードパーティアプリケーションアクセスポリシー（Access restricted / No restriction）の管理、保留中アクセスリクエストの承認 [^30]

### Personal access tokens > Settings

> パス: `/organizations/{org}/settings/personal-access-tokens`

- Fine-grained PAT ポリシー（Allow / Restrict）、管理者承認要件、最大有効期間の設定 [^31]

### Personal access tokens > Active tokens

> パス: `/organizations/{org}/settings/personal-access-tokens/active`

- Org にアクセスするアクティブな Fine-grained PAT の一覧

### Personal access tokens > Pending requests

> パス: `/organizations/{org}/settings/personal-access-token-requests`

- 保留中の PAT アクセスリクエストの確認・承認

## Integrations

### Scheduled reminders

> パス: `/organizations/{org}/settings/reminders`

- チームへのプルリクエストレビューのスケジュールリマインダーの作成 [^32]

## Messages

### Announcement

> パス: `/organizations/{org}/settings/announcement`

- Org 全ページに表示するアナウンスメントバナーの作成。有効期限の設定、ユーザーによる非表示の許可が可能 [^33]

## Archive

### Logs > Audit log

> パス: `/organizations/{org}/settings/audit-log`

- 監査ログの検索・フィルタリング・エクスポート（Git イベントのエクスポート含む、上限 100 MB） [^34]

### Deleted repositories

> パス: `/organizations/{org}/settings/deleted_repositories`

- 削除済みリポジトリの一覧表示・復元（Private 状態で復元、チーム / コラボレーター権限は復元されない）

## Developer settings

### OAuth Apps

> パス: `/organizations/{org}/settings/applications`

- Org 所有の OAuth アプリケーションの登録・管理

### GitHub Apps

> パス: `/organizations/{org}/settings/apps`

- Org 所有の GitHub Apps の登録・管理。アプリ管理権限の設定（Org ロール割り当て経由）

---

[^1]: [GitHub Docs: Managing your organization's settings](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings)
[^2]: [GitHub Docs: Managing the display of member names](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/managing-the-display-of-member-names-in-your-organization)
[^3]: [GitHub Docs: Governing how people use repositories](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/governing-how-people-use-repositories-in-your-organization)
[^4]: [GitHub Docs: About billing for your enterprise](https://docs.github.com/en/enterprise-cloud@latest/billing/managing-your-github-billing-settings/about-billing-for-your-enterprise)
[^5]: [GitHub Docs: Managing custom organization roles](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-peoples-access-to-your-organization-with-roles/managing-custom-organization-roles)
[^6]: [GitHub Docs: Managing custom repository roles](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-peoples-access-to-your-organization-with-roles/managing-custom-repository-roles-for-an-organization)
[^7]: [GitHub Docs: Setting base permissions for an organization](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-user-access-to-your-organizations-repositories/managing-repository-roles/setting-base-permissions-for-an-organization)
[^8]: [GitHub Docs: Blocking a user from your organization](https://docs.github.com/en/enterprise-cloud@latest/communities/maintaining-your-safety-on-github/blocking-a-user-from-your-organization)
[^9]: [GitHub Docs: Limiting interactions in your organization](https://docs.github.com/en/enterprise-cloud@latest/communities/moderating-comments-and-conversations/limiting-interactions-in-your-organization)
[^10]: [GitHub Docs: Managing pull request reviews](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/managing-pull-request-reviews-in-your-organization)
[^11]: [GitHub Docs: Managing GitHub Pages publication](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/managing-the-publication-of-github-pages-sites-for-your-organization)
[^12]: [GitHub Docs: Allowing people to delete issues](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/allowing-people-to-delete-issues-in-your-organization)
[^13]: [GitHub Docs: Setting team creation permissions](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/setting-team-creation-permissions-in-your-organization)
[^14]: [GitHub Docs: Changing visibility of dependency insights](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/changing-the-visibility-of-your-organizations-dependency-insights)
[^15]: [GitHub Docs: Managing the default branch name](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/managing-the-default-branch-name-for-repositories-in-your-organization)
[^16]: [GitHub Docs: Creating rulesets for repositories](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/creating-rulesets-for-repositories-in-your-organization)
[^17]: [GitHub Docs: Managing custom properties for repositories](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/managing-custom-properties-for-repositories-in-your-organization)
[^18]: [GitHub Docs: Managing Codespaces for your organization](https://docs.github.com/en/enterprise-cloud@latest/codespaces/managing-codespaces-for-your-organization)
[^19]: [GitHub Docs: Disabling projects in your organization](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/disabling-project-boards-in-your-organization)
[^20]: [GitHub Docs: Managing Copilot in your organization](https://docs.github.com/en/enterprise-cloud@latest/copilot/managing-copilot/managing-github-copilot-in-your-organization)
[^21]: [GitHub Docs: Managing Copilot policies](https://docs.github.com/en/enterprise-cloud@latest/copilot/managing-copilot/managing-policies-and-features-for-copilot-in-your-organization)
[^22]: [GitHub Docs: Excluding content from Copilot](https://docs.github.com/en/enterprise-cloud@latest/copilot/managing-copilot/managing-github-copilot-in-your-organization/setting-policy-for-copilot-in-your-organization)
[^23]: [GitHub Docs: Disabling or limiting GitHub Actions](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/disabling-or-limiting-github-actions-for-your-organization)
[^24]: [GitHub Docs: Enabling or disabling GitHub Discussions](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/enabling-or-disabling-github-discussions-for-an-organization)
[^25]: [GitHub Docs: About networking for hosted compute](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/about-networking-for-hosted-compute-products-in-your-organization)
[^26]: [GitHub Docs: Managing security settings for your organization](https://docs.github.com/en/enterprise-cloud@latest/organizations/keeping-your-organization-secure/managing-security-settings-for-your-organization)
[^27]: [GitHub Docs: Managing GitHub Advanced Security](https://docs.github.com/en/enterprise-cloud@latest/organizations/keeping-your-organization-secure/managing-security-settings-for-your-organization/managing-security-and-analysis-settings-for-your-organization)
[^28]: [GitHub Docs: Restricting deploy keys](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/restricting-deploy-keys-in-your-organization)
[^29]: [GitHub Docs: Verifying or approving a domain](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/verifying-or-approving-a-domain-for-your-organization)
[^30]: [GitHub Docs: About OAuth app access restrictions](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-oauth-access-to-your-organizations-data/about-oauth-app-access-restrictions)
[^31]: [GitHub Docs: Setting a personal access token policy](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-programmatic-access-to-your-organization/setting-a-personal-access-token-policy-for-your-organization)
[^32]: [GitHub Docs: Managing scheduled reminders](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/managing-scheduled-reminders-for-your-organization)
[^33]: [GitHub Docs: Creating an announcement banner](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-organization-settings/creating-an-announcement-banner-for-your-organization)
[^34]: [GitHub Docs: Reviewing the audit log](https://docs.github.com/en/enterprise-cloud@latest/organizations/keeping-your-organization-secure/managing-security-settings-for-your-organization/reviewing-the-audit-log-for-your-organization)
