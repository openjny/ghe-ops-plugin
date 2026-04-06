# Enterprise Policies

> パス: `/enterprises/{enterprise}/settings/policies/repositories`

## 概要

Enterprise レベルのポリシー設定。リポジトリ操作、メンバー権限、Codespaces、Copilot、Actions、セキュリティなど多岐にわたるポリシーを Organization に対して強制する。[^1]

## ナビゲーション

| 項目 | パス |
|------|------|
| Repository | `/enterprises/{enterprise}/settings/policies/repositories` |
| Repository > Repository | `/enterprises/{enterprise}/settings/policies/repositories` |
| Repository > Code | `/enterprises/{enterprise}/settings/policies/code` |
| Repository > Code insights | `/enterprises/{enterprise}/settings/policies/code/insights` |
| Repository > Code ruleset bypasses | `/enterprises/{enterprise}/settings/policies/code/bypass_requests` |
| Repository > Custom properties | `/enterprises/{enterprise}/settings/custom-properties` |
| Member privileges | `/enterprises/{enterprise}/settings/member_privileges` |
| Codespaces | `/enterprises/{enterprise}/settings/codespaces` |
| Copilot | `/enterprises/{enterprise}/settings/copilot` |
| Actions | `/enterprises/{enterprise}/settings/actions` |
| Hosted compute networking | `/enterprises/{enterprise}/settings/hosted_compute_networking` |
| Projects | `/enterprises/{enterprise}/settings/projects` |
| Advanced Security | `/enterprises/{enterprise}/settings/security_analysis_policies` |
| Code Quality | `/enterprises/{enterprise}/settings/code_quality_policies` |
| Personal access tokens | `/enterprises/{enterprise}/settings/personal-access-tokens` |

## Repository policies

> パス: `/enterprises/{enterprise}/settings/policies/repositories`

リポジトリに対する操作（削除、転送など）のポリシーを定義する。ルールセットベース。[^2]

### UI 要素

- アクションボタン: 「New policy」（新規ポリシー作成）
- ポリシー一覧テーブル（作成済みの場合）

## Code

> パス: `/enterprises/{enterprise}/settings/policies/code`

コードに対するルールセットベースのポリシーを定義する。ブランチ・タグの保護ルールやプッシュルールを Enterprise レベルで適用できる。[^7]

### UI 要素

- アクションボタン: 「New ruleset」（新規ルールセット作成）
- ルールセット一覧テーブル（作成済みの場合）

## Code insights

> パス: `/enterprises/{enterprise}/settings/policies/code/insights`

ルールセットの適用状況を確認するインサイトページ。ルールセットの Evaluate モードで違反をモニタリングできる。

### UI 要素

- フィルターフォーム: ルールインサイトの絞り込み
- ルール適用結果一覧

## Code ruleset bypasses

> パス: `/enterprises/{enterprise}/settings/policies/code/bypass_requests`

ルールセットのバイパスリクエストを管理するページ。バイパスリストに含まれるアクターがリクエストを承認・管理できる。

### UI 要素

- フィルターフォーム: バイパスリクエストの絞り込み
- リクエスト一覧

## Custom properties

> パス: `/enterprises/{enterprise}/settings/custom-properties`

Enterprise レベルのカスタムプロパティを定義・管理する。リポジトリにメタデータ（コンプライアンスフレームワーク、データ機密度等）を付与し、ルールセットやポリシーのターゲティングに利用できる。Enterprise あたり最大 100 個のプロパティ定義が可能。[^8]

### UI 要素

- アクションリンク: 「New property」（新規プロパティ作成）
- プロパティ一覧テーブル（作成済みの場合）

## Member privileges

> パス: `/enterprises/{enterprise}/settings/member_privileges`

Enterprise メンバーのデフォルト権限を設定。[^6]

- Base permissions: Org リポジトリへのベース権限（No policy / 特定の権限レベルを強制）
- Repository creation: メンバーのリポジトリ作成許可（No policy / Disabled / Members can create repositories（Private / Internal））
  - Block the creation of user namespace repositories: EMU ユーザー名前空間のリポジトリ作成をブロック
- Repository forking: プライベート・インターナルリポジトリのフォーク許可（No policy / Enabled / Disabled）
- Repository collaborators: リポジトリコラボレーターの招待権限（Enterprise owners only 等）
- Default branch name: 新規リポジトリのデフォルトブランチ名、Enterprise 全体での強制オプション
- Deploy keys: デプロイキーの利用（No policy / Disabled / Enabled）
- Admin repository permissions:
  - Repository visibility change: リポジトリ可視性の変更許可（No policy / Enabled / Disabled）
  - Repository deletion and transfer: プライベートリポジトリの削除・転送許可（No policy / Enabled / Disabled）
  - Repository issue deletion: Issue の削除許可（No policy / Enabled / Disabled）

## Codespaces

> パス: `/enterprises/{enterprise}/settings/codespaces`

GitHub Codespaces の Org アクセス管理。

- Manage organization access to GitHub Codespaces（Enable for all organizations / Enable for specific organizations / Disabled）

## Copilot

> パス: `/enterprises/{enterprise}/settings/copilot`

AI Controls > Copilot ページにリダイレクトされる。詳細は [enterprise-ai-controls.md](./enterprise-ai-controls.md) の Copilot セクションを参照。

## Actions

> パス: `/enterprises/{enterprise}/settings/actions`

GitHub Actions の利用ポリシー、ランナー、カスタムイメージ、OIDC 構成。[^3]

### サブタブ

| 項目 | パス |
|------|------|
| Policies | `/enterprises/{enterprise}/settings/actions` |
| Runners | `/enterprises/{enterprise}/settings/actions/runners` |
| Runner groups | `/enterprises/{enterprise}/settings/actions/runner-groups` |
| Custom images | `/enterprises/{enterprise}/settings/actions/custom-images` |
| OIDC Configuration | `/enterprises/{enterprise}/settings/actions/oidc-configuration` |

### Policies

- Actions の有効化（Enable for all organizations / Enable for specific organizations / Disabled）
- 許可するアクション（Allow all / Allow enterprise actions only / Allow enterprise + select non-enterprise actions）
- アクションのコミット SHA ピン留め必須化

### Runners

- Repository self-hosted runners: リポジトリレベルのセルフホストランナーの許可（Disable for all organizations / Disable for all EMU repositories）

### Custom images

- カスタムイメージの利用（Enable for all / Enable for specific organizations / Disabled）
- Custom images retention: Maximum versions per image / Unused version retention / Maximum version age

### Artifact and log retention

- アーティファクトとログの保持日数（デフォルト: 90日、Org は短くのみ設定可）

### Cache

- Cache retention: キャッシュ保持日数（最大365日）
- Cache size eviction limit: キャッシュサイズ上限（最大10000GB）

### Fork pull request workflows

- プライベート・インターナルリポジトリのフォーク PR からのワークフロー実行許可

### Workflow permissions

- GITHUB_TOKEN のデフォルト権限（Read and write / Read repository contents and packages）
- GitHub Actions による PR 作成・承認の許可

## Hosted compute networking

> パス: `/enterprises/{enterprise}/settings/hosted_compute_networking`

Org によるネットワーク構成作成の許可。

- Manage creation of network configurations for organizations（Enabled / Disabled）
  - Enabled: Org オーナーが独自のネットワーク構成を作成可能
  - Disabled: Enterprise が作成した構成のみ使用可能

## Projects

> パス: `/enterprises/{enterprise}/settings/projects`

Projects の利用ポリシー。

- Organization projects: メンバーのプロジェクト作成許可（No policy / Enabled / Disabled）
- Project visibility change permission: プロジェクトの可視性変更許可（No policy / Enabled / Disabled）

## Advanced Security

> パス: `/enterprises/{enterprise}/settings/security_analysis_policies`

GitHub Advanced Security（GHAS）の有効化ポリシー。Settings > Advanced Security（構成管理）とは別ページ。[^4]

### サブタブ

| 項目 | パス |
|------|------|
| Policies | `/enterprises/{enterprise}/settings/security_analysis_policies` |
| Security features | `/enterprises/{enterprise}/settings/security_analysis_policies/security_features` |

### Policies

#### General

- Availability: Advanced Security プランの Org アクセス許可（Allow for all organizations / Allow for specific organizations / Disabled）

#### Secret Protection

- Repository Admins can Enable or Disable Secret Protection（Allowed / Not allowed）
- AI detection in secret scanning（Allowed / Not allowed）

#### Code Security

- Repository Admins can Enable or Disable GitHub Code Security（Allowed / Not allowed）
- Copilot Autofix: CodeQL アラートへの AI 修正提案の許可（Allowed / Not allowed）
- Enable or disable Dependabot alerts by repository admins（Allowed / Not allowed）
- Dependency Insights: 依存関係のセキュリティアドバイザリ・ライセンス表示（No policy / Enabled / Disabled）

### Security features

- Secret Protection custom patterns: Enterprise レベルのシークレットスキャン用カスタムパターン管理（最大 500 パターン）[^9]
  - アクションリンク: 「New pattern」（新規カスタムパターン作成）
  - パターン一覧（フィルター: is:published / is:unpublished）

## Code Quality (Preview)

> パス: `/enterprises/{enterprise}/settings/code_quality_policies`

コード品質に関するポリシー。

- Organization Access: Code Quality の Org アクセス許可（Allow for all organizations / Allow for specific organizations / Disabled）
- Repository Admin Policy: リポジトリ管理者による Code Quality の有効化/無効化許可（Allowed / Not allowed）

## Personal access tokens

> パス: `/enterprises/{enterprise}/settings/personal-access-tokens`

PAT（Personal Access Token）の利用ポリシー。Fine-grained tokens タブと Tokens (classic) タブに分かれる。[^5]

### Fine-grained tokens

- Restrict access via fine-grained personal access tokens（Allow organizations to configure / Restrict access / Allow access）
- Require approval of fine-grained personal access tokens（Allow organizations to configure / Require approval flow / Disable approval flow）
- Set maximum lifetimes: 有効期限の上限設定（7 / 30 / 60 / 90 / 366 days / Custom）、Enterprise 管理者の免除オプション

### Tokens (classic)

- Restrict personal access tokens (classic) from accessing your organizations（Allow organizations to configure / Restrict access / Allow access）
- Set a maximum lifetime for personal access tokens (classic)
  - Personal access tokens (classic) must expire: 有効期限の必須化

---

[^1]: [GitHub Docs: Enforcing policies for your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/enforcing-policies)
[^2]: [GitHub Docs: About rulesets](https://docs.github.com/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets)
[^3]: [GitHub Docs: Enforcing policies for GitHub Actions in your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/enforcing-policies/enforcing-policies-for-your-enterprise/enforcing-policies-for-github-actions-in-your-enterprise)
[^4]: [GitHub Docs: About GitHub Advanced Security](https://docs.github.com/enterprise-cloud@latest/get-started/learning-about-github/about-github-advanced-security)
[^5]: [GitHub Docs: Setting a personal access token policy for your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/enforcing-policies/enforcing-policies-for-your-enterprise/enforcing-policies-for-personal-access-tokens-in-your-enterprise)
[^6]: [GitHub Docs: Enforcing policies for member privileges](https://docs.github.com/enterprise-cloud@latest/admin/enforcing-policies/enforcing-policies-for-your-enterprise/enforcing-repository-management-policies-in-your-enterprise)
[^7]: [GitHub Docs: Enforcing code governance in your enterprise with rulesets](https://docs.github.com/enterprise-cloud@latest/admin/enforcing-policies/enforcing-policies-for-your-enterprise/enforcing-policies-for-code-governance)
[^8]: [GitHub Docs: Managing custom properties for repositories in your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-repositories-in-your-enterprise/managing-custom-properties-for-repositories-in-your-enterprise)
[^9]: [GitHub Docs: Defining custom patterns for secret scanning](https://docs.github.com/enterprise-cloud@latest/code-security/secret-scanning/using-advanced-secret-scanning-and-push-protection-features/custom-patterns/defining-custom-patterns-for-secret-scanning)
