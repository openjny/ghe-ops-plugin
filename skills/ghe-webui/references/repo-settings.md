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
| Agents | `/{owner}/{repo}/agents` |
| Actions | `/{owner}/{repo}/actions` |
| Projects | `/{owner}/{repo}/projects` |
| Wiki | `/{owner}/{repo}/wiki` |
| Security and quality | `/{owner}/{repo}/security` |
| Insights | `/{owner}/{repo}/pulse` |
| Settings | `/{owner}/{repo}/settings` |

## Settings サイドナビゲーション

### General

> パス: `/{owner}/{repo}/settings`

- リポジトリ名の変更
- テンプレートリポジトリの設定 [^2]
- デフォルトブランチの変更（名前変更・切り替え）[^3]
- Releases: リリースの不変性設定（Enable release immutability）
- Features の有効/無効:
  - Wikis（編集制限: push 権限を持つチームのみに制限可）
  - Issues（テンプレートの設定リンクあり）
  - Allow forking（Enterprise ポリシーにより無効化される場合あり）
  - Discussions
  - Projects
  - Pull requests（Pull request permissions: 作成を許可するユーザーの制限が可能）
- Pull Requests:
  - マージ戦略設定（Allow merge commits / Allow squash merging / Allow rebase merging）。各戦略にデフォルトコミットメッセージの設定あり
  - Always suggest updating pull request branches
  - Allow auto-merge [^4]
  - Automatically delete head branches
- Commits:
  - Require contributors to sign off on web-based commits [^5]
  - Allow comments on individual commits
- Archives: Include Git LFS objects in archives [^6]
- Pushes: Limit how many branches and tags can be updated in a single push [^7]
- Issues: Auto-close issues with merged linked pull requests [^8]
- Danger Zone: リポジトリの可視性変更、ブランチ保護ルールの無効化、所有権の転送、アーカイブ、削除

### Access

| 項目 | パス |
|------|------|
| Collaborators and teams | `/{owner}/{repo}/settings/access` |
| Team and member roles | `/{owner}/{repo}/settings/role_details` |

#### Collaborators and teams

> パス: `/{owner}/{repo}/settings/access`

- リポジトリの可視性表示と管理リンク
- Base role の表示（Enterprise メンバー全体のデフォルト権限）
- Direct access / Organization access / Enterprise access (Preview) のタブ切り替え
- コラボレーターの追加（Add people / Add teams / Create team）
- ユーザー・チームごとのロール変更、アクセス削除
- Type / Role によるフィルタリング [^9]

#### Team and member roles

> パス: `/{owner}/{repo}/settings/role_details`

- リポジトリで利用可能なロール一覧の表示
- Pre-defined roles: Read, Triage, Write, Maintain, Admin
- Custom roles: Organization 管理者が作成・管理するカスタムロールの一覧 [^10]

### Code and automation

| 項目 | パス |
|------|------|
| Branches | `/{owner}/{repo}/settings/branches` |
| Tags | `/{owner}/{repo}/settings/tag_protection` |
| **Rules** | |
| ↳ Rulesets | `/{owner}/{repo}/settings/rules` |
| ↳ Insights | `/{owner}/{repo}/settings/rules/insights` |
| ↳ Bypass requests | `/{owner}/{repo}/settings/rules/bypass_requests` |
| **Actions** | |
| ↳ General | `/{owner}/{repo}/settings/actions` |
| ↳ Runners | `/{owner}/{repo}/settings/actions/runners` |
| ↳ OIDC | `/{owner}/{repo}/settings/actions/oidc-configuration` |
| Webhooks | `/{owner}/{repo}/settings/hooks` |
| **Copilot** | |
| ↳ Content exclusion | `/{owner}/{repo}/settings/copilot/content_exclusion` |
| ↳ Code review | `/{owner}/{repo}/settings/copilot/code_review` |
| ↳ Cloud agent | `/{owner}/{repo}/settings/copilot/coding_agent` |
| Environments | `/{owner}/{repo}/settings/environments` |
| Pages | `/{owner}/{repo}/settings/pages` |
| Custom properties | `/{owner}/{repo}/settings/custom-properties` |

#### Branches

> パス: `/{owner}/{repo}/settings/branches`

- ブランチ保護ルール（classic）の一覧表示と作成
- ブランチ Ruleset の作成リンク（推奨）
- classic branch protection rule の追加 [^11]

#### Tags

> パス: `/{owner}/{repo}/settings/tag_protection`

- Protected tags は非推奨。Rulesets への移行が推奨されている
- タグ Ruleset への移行リンク [^12]

#### Rules > Rulesets

> パス: `/{owner}/{repo}/settings/rules`

- リポジトリレベルの Ruleset 一覧表示
- 新規 Ruleset の作成 [^12]

#### Rules > Insights

> パス: `/{owner}/{repo}/settings/rules/insights`

- ルール評価の Insights 表示
- 期間（day）・ステータス（active / evaluate）によるフィルタリング
- evaluate モードの Ruleset の影響を事前確認可能

#### Rules > Bypass requests

> パス: `/{owner}/{repo}/settings/rules/bypass_requests`

- Bypass request の一覧表示と管理
- ルール違反を伴う操作について bypass リクエストの承認・却下
- 期間によるフィルタリング

#### Actions > General

> パス: `/{owner}/{repo}/settings/actions`

- Actions permissions:
  - Allow all actions and reusable workflows
  - Disable actions
  - Allow enterprise actions and reusable workflows
  - Allow enterprise, and select non-enterprise, actions and reusable workflows（コミット SHA ピン留め要求オプションあり）
- Artifact and log retention: 保持日数の設定（Organization の上限あり）
- Cache: キャッシュ保持日数と最大サイズの設定（Enterprise の上限あり）
- Fork pull request workflows: フォーク PR からのワークフロー実行許可
- Workflow permissions:
  - Read and write permissions / Read repository contents and packages permissions
  - Allow GitHub Actions to create and approve pull requests
- Access: 他のリポジトリからの Actions コンポーネント利用可否（Not accessible / Organization / Enterprise）[^13]

#### Actions > Runners

> パス: `/{owner}/{repo}/settings/actions/runners`

- Self-hosted runner の一覧と登録 [^14]

#### Actions > OIDC

> パス: `/{owner}/{repo}/settings/actions/oidc-configuration`

- OIDC トークンの subject claim のカスタマイズ
- デフォルトテンプレート使用 or カスタムテンプレートの設定 [^15]

#### Webhooks

> パス: `/{owner}/{repo}/settings/hooks`

- Webhook の一覧表示と追加
- 特定イベント発生時に外部サービスへ POST 通知を送信
- Organization の Webhook も適用される旨の表示 [^16]

#### Copilot > Content exclusion

> パス: `/{owner}/{repo}/settings/copilot/content_exclusion`

- Copilot がアクセスしないパスの指定（リポジトリ内パス）
- リポジトリレベルの除外設定は Enterprise 全メンバーに適用 [^17]

#### Copilot > Code review

> パス: `/{owner}/{repo}/settings/copilot/code_review`

- Copilot を PR レビュアーとして追加可能
- General settings: カスタム指示の使用（On/Off）
- Ruleset と連携した自動レビューリクエスト設定
- push 時の自動コードレビュー [^18]

#### Copilot > Cloud agent

> パス: `/{owner}/{repo}/settings/copilot/coding_agent`

- Copilot cloud agent の設定
- Internet access:
  - Enable firewall（推奨）: 許可リストの URL のみにアクセスを制限
  - Recommended allowlist（ツール・パッケージ・依存関係のインストール用）
  - Custom allowlist: 特定のドメイン、IP アドレス、URL を許可
- Actions workflow approval: Copilot がプッシュした変更に対するワークフロー実行の承認要求（推奨）
- Validation tools:
  - CodeQL code scanning（推奨）
  - Copilot code review（推奨）
  - Secret scanning（推奨）
  - Dependency vulnerability checks（推奨）
- Model Context Protocol (MCP): MCP サーバーの JSON 設定 [^19]

#### Environments

> パス: `/{owner}/{repo}/settings/environments`

- デプロイ環境の一覧表示と新規作成
- 環境ごとに保護ルール、変数、シークレットを設定可能 [^20]

#### Pages

> パス: `/{owner}/{repo}/settings/pages`

- GitHub Pages のビルド・デプロイ設定
- Source: Deploy from a branch
- Branch の選択（None で無効化）[^21]

#### Custom properties

> パス: `/{owner}/{repo}/settings/custom-properties`

- リポジトリにカスタムプロパティ（コンプライアンスフレームワーク、データ感度、プロジェクト詳細等）を付与
- Organization で定義されたプロパティの値を設定 [^22]

### Security and quality

| 項目 | パス |
|------|------|
| Advanced Security | `/{owner}/{repo}/settings/security_analysis` |
| Code quality | `/{owner}/{repo}/settings/code-quality` |
| Deploy keys | `/{owner}/{repo}/settings/keys` |
| **Secrets and variables** | |
| ↳ Actions | `/{owner}/{repo}/settings/secrets/actions` |
| ↳ Codespaces | `/{owner}/{repo}/settings/secrets/codespaces` |
| ↳ Dependabot | `/{owner}/{repo}/settings/secrets/dependabot` |

#### Advanced Security

> パス: `/{owner}/{repo}/settings/security_analysis`

- Secret Protection の有効化（90 日アクティブコミッター単位で課金）
- Code Security の有効化（90 日アクティブコミッター単位で課金）
- Dependency graph の有効化
- Dependabot:
  - Dependabot alerts の有効化
  - Dependabot security updates の有効化
  - Grouped security updates の有効化
  - Dependabot version updates の有効化
  - Dependabot on self-hosted runners の有効化 [^23]

#### Code quality

> パス: `/{owner}/{repo}/settings/code-quality`

- Code quality (Preview) の有効化
- コードベースの信頼性、保守性、効率性をプロアクティブにスキャン
- 有効化すると Actions minutes が課金される [^24]

#### Deploy keys

> パス: `/{owner}/{repo}/settings/keys`

- Deploy key の一覧と追加
- SSH 鍵で単一リポジトリに readonly または write アクセスを付与
- Enterprise ポリシーにより無効化される場合あり
- GitHub Apps の利用が推奨されている [^25]

#### Secrets and variables > Actions

> パス: `/{owner}/{repo}/settings/secrets/actions`

- Actions 用のシークレットと変数を管理
- Secrets タブ / Variables タブの切り替え
- スコープ: Environment secrets / Repository secrets / Organization secrets
- コラボレーター権限を持つユーザーが利用可能
- フォーク PR にはシークレットを渡さない [^26]

#### Secrets and variables > Codespaces

> パス: `/{owner}/{repo}/settings/secrets/codespaces`

- Codespaces 用のシークレットを管理
- スコープ: Repository secrets / Organization secrets [^27]

#### Secrets and variables > Dependabot

> パス: `/{owner}/{repo}/settings/secrets/dependabot`

- Dependabot 用のシークレットを管理
- スコープ: Repository secrets / Organization secrets
- フォークにはシークレットを渡さない [^28]

### Integrations

| 項目 | パス |
|------|------|
| GitHub Apps | `/{owner}/{repo}/settings/installations` |
| Email notifications | `/{owner}/{repo}/settings/notifications` |
| Autolink references | `/{owner}/{repo}/settings/key_links` |

#### GitHub Apps

> パス: `/{owner}/{repo}/settings/installations`

- リポジトリにインストール済みの GitHub Apps の一覧表示
- GitHub Apps でワークフローを拡張 [^29]

#### Email notifications

> パス: `/{owner}/{repo}/settings/notifications`

- push イベント時にメール通知を送信するアドレスの設定（最大2つ）
- Approved header の設定（モデレートされたメーリングリストの自動承認用）
- Active / Inactive の切り替え [^30]

#### Autolink references

> パス: `/{owner}/{repo}/settings/key_links`

- カスタム Autolink reference の追加
- GitHub 外の URL への自動リンク変換を設定
- alphanumeric または numeric 形式を選択可能 [^31]

---

[^1]: [GitHub Docs: Managing repository settings](https://docs.github.com/enterprise-cloud@latest/repositories/managing-your-repositorys-settings-and-features)
[^2]: [GitHub Docs: Creating a repository from a template](https://docs.github.com/enterprise-cloud@latest/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template)
[^3]: [GitHub Docs: Managing the default branch name](https://docs.github.com/enterprise-cloud@latest/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/managing-the-default-branch-name-for-your-repositories)
[^4]: [GitHub Docs: Automatically merging a pull request](https://docs.github.com/enterprise-cloud@latest/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/automatically-merging-a-pull-request)
[^5]: [GitHub Docs: Managing the commit signoff policy](https://docs.github.com/enterprise-cloud@latest/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/managing-the-commit-signoff-policy-for-your-repository)
[^6]: [GitHub Docs: Managing Git LFS objects in archives](https://docs.github.com/enterprise-cloud@latest/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/managing-git-lfs-objects-in-archives-of-your-repository)
[^7]: [GitHub Docs: Managing the push policy](https://docs.github.com/enterprise-cloud@latest/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/managing-the-push-policy-for-your-repository)
[^8]: [GitHub Docs: Managing auto-closing issues](https://docs.github.com/enterprise-cloud@latest/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/managing-auto-closing-issues)
[^9]: [GitHub Docs: Managing teams and people with access](https://docs.github.com/enterprise-cloud@latest/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/managing-teams-and-people-with-access-to-your-repository)
[^10]: [GitHub Docs: Managing custom repository roles](https://docs.github.com/enterprise-cloud@latest/organizations/managing-peoples-access-to-your-organization-with-roles/managing-custom-repository-roles-for-an-organization)
[^11]: [GitHub Docs: About protected branches](https://docs.github.com/enterprise-cloud@latest/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches)
[^12]: [GitHub Docs: About rulesets](https://docs.github.com/enterprise-cloud@latest/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets)
[^13]: [GitHub Docs: Managing GitHub Actions settings for a repository](https://docs.github.com/enterprise-cloud@latest/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-github-actions-settings-for-a-repository)
[^14]: [GitHub Docs: About self-hosted runners](https://docs.github.com/enterprise-cloud@latest/actions/hosting-your-own-runners/managing-self-hosted-runners/about-self-hosted-runners)
[^15]: [GitHub Docs: About OIDC for GitHub Actions](https://docs.github.com/enterprise-cloud@latest/actions/security-for-github-actions/security-hardening-your-deployments/about-security-hardening-with-openid-connect)
[^16]: [GitHub Docs: About webhooks](https://docs.github.com/enterprise-cloud@latest/webhooks/about-webhooks)
[^17]: [GitHub Docs: Excluding content from Copilot](https://docs.github.com/enterprise-cloud@latest/copilot/managing-copilot/managing-github-copilot-in-your-organization/setting-up-github-copilot-for-your-organization/excluding-content-from-github-copilot)
[^18]: [GitHub Docs: Using Copilot code review](https://docs.github.com/enterprise-cloud@latest/copilot/using-github-copilot/code-review/using-copilot-code-review)
[^19]: [GitHub Docs: About Copilot coding agent](https://docs.github.com/enterprise-cloud@latest/copilot/using-github-copilot/using-copilot-coding-agent-to-work-on-tasks/about-assigning-tasks-to-copilot)
[^20]: [GitHub Docs: Managing environments for deployment](https://docs.github.com/enterprise-cloud@latest/actions/managing-workflow-runs-and-deployments/managing-deployments/managing-environments-for-deployment)
[^21]: [GitHub Docs: Configuring a publishing source for GitHub Pages](https://docs.github.com/enterprise-cloud@latest/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
[^22]: [GitHub Docs: Managing custom properties](https://docs.github.com/enterprise-cloud@latest/organizations/managing-organization-settings/managing-custom-properties-for-repositories-in-your-organization)
[^23]: [GitHub Docs: Managing security and analysis settings](https://docs.github.com/enterprise-cloud@latest/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-security-and-analysis-settings-for-your-repository)
[^24]: [GitHub Docs: About code quality](https://docs.github.com/enterprise-cloud@latest/code-security/code-scanning/managing-your-code-scanning-configuration/about-the-tool-status-page)
[^25]: [GitHub Docs: Managing deploy keys](https://docs.github.com/enterprise-cloud@latest/authentication/connecting-to-github-with-ssh/managing-deploy-keys)
[^26]: [GitHub Docs: Using secrets in GitHub Actions](https://docs.github.com/enterprise-cloud@latest/actions/security-for-github-actions/security-guides/using-secrets-in-github-actions)
[^27]: [GitHub Docs: Managing secrets for Codespaces](https://docs.github.com/enterprise-cloud@latest/codespaces/managing-codespaces-for-your-organization/managing-development-environment-secrets-for-your-repository-or-organization)
[^28]: [GitHub Docs: Configuring Dependabot secrets](https://docs.github.com/enterprise-cloud@latest/code-security/dependabot/working-with-dependabot/configuring-access-to-private-registries-for-dependabot)
[^29]: [GitHub Docs: About GitHub Apps](https://docs.github.com/enterprise-cloud@latest/apps/overview)
[^30]: [GitHub Docs: About email notifications for pushes](https://docs.github.com/enterprise-cloud@latest/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/about-email-notifications-for-pushes-to-your-repository)
[^31]: [GitHub Docs: Configuring autolinks](https://docs.github.com/enterprise-cloud@latest/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/configuring-autolinks-to-reference-external-resources)
