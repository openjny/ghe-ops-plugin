# Enterprise Settings

> パス: `/enterprises/{enterprise}/settings/profile`

## 概要

Enterprise の一般設定、認証セキュリティ、セキュリティ機能構成、ドメイン管理、Audit ログ、Webhook、ネットワーク構成、GitHub Apps、アナウンスメント、サポート設定を管理する。

## サイドナビゲーション

| 項目 | パス |
|------|------|
| General | `/enterprises/{enterprise}/settings/profile` |
| Authentication security | `/enterprises/{enterprise}/settings/security` |
| Advanced Security | `/enterprises/{enterprise}/settings/security_analysis` |
| Verified & approved domains | `/enterprises/{enterprise}/settings/domains` |
| Audit log | `/enterprises/{enterprise}/settings/audit-log` |
| Retired namespaces | `/enterprises/{enterprise}/settings/retired_namespaces` |
| Hooks | `/enterprises/{enterprise}/settings/hooks` |
| Hosted compute networking | `/enterprises/{enterprise}/settings/network_configurations` |
| GitHub Apps | `/enterprises/{enterprise}/settings/apps` |
| Announcement | `/enterprises/{enterprise}/settings/announcement` |
| Support | `/enterprises/{enterprise}/settings/support` |

## セクション: General

Enterprise のプロフィール情報と外観設定。

- Enterprise の表示名、説明、Web サイト URL、所在地、セキュリティ連絡先メールを設定できる
- プロフィール画像をアップロードできる
- Hosting region と Enterprise URL の表示（読み取り専用）
- Profile name visibility: メンバーのプロフィール名をハンドルと一緒に表示するか（Let organizations decide / Enabled / Disabled）[^1]
- Custom footer: Enterprise 全体のフッターにカスタムリンクを追加（最大4つ）

## セクション: Authentication security

認証に関するセキュリティ設定。[^2]

- SSH certificate authorities: SSH 証明書認証局の登録・管理
- IP allow list: IP アドレスベースのアクセス制限（Enabled / Disabled）[^3]
- Credentials: Enterprise 内の認証情報の概要と管理
  - Fine-grained personal access tokens の一覧
  - Personal access tokens (classic) の一覧
  - SSH keys の一覧
  - GitHub App / OAuth app user access tokens の一覧
- Danger zone: SSO 認証の一括取り消し、トークン・キーの一括削除

## セクション: Advanced Security

GitHub Advanced Security（GHAS）の構成管理。Policies の Advanced Security とは別ページ。[^4]

- カバレッジ状況: Dependabot、Code Security、Secret Protection の保護率
- Configurations: セキュリティ構成の作成・管理（「GitHub recommended」等のプリセット含む）
- Additional Settings:
  - Secret Protection: push protection のパターン設定、リソースリンク設定
  - User namespace repositories: ユーザー名前空間リポジトリへの Secret Protection 有効化（Enable all / Disable all）、新規リポジトリへの自動有効化（On / Off）

## セクション: Verified & approved domains

Enterprise のドメイン検証と承認。メール通知やプロフィールの URL 検証に使用。[^5]

## セクション: Audit log

Enterprise の監査ログ。ユーザー・Org・リポジトリのアクティビティの検索・エクスポート。[^6]

## セクション: Retired namespaces

名前変更や削除された Org・ユーザーの旧名前空間の管理。リタイアされた名前空間の一覧と復元操作。

## セクション: Hooks

Enterprise 全体の Webhook の作成・管理。イベントの選択と配信先 URL の設定。

## セクション: Hosted compute networking

GitHub-hosted runners のネットワーク構成。Azure VNET への接続設定。[^7]

## セクション: GitHub Apps

Enterprise にインストールされた GitHub Apps の一覧と管理。アプリのアクセス許可の確認。

## セクション: Announcement

Enterprise 全体に表示するアナウンスメントバナーの作成・管理。メッセージと表示期間の設定。

## セクション: Support

GitHub Support のエンタイトルメント管理。サポートチケットの優先度設定。

Enterprise 全体に表示するアナウンスメントバナーの設定。

## セクション: Support

> パス: `/enterprises/{enterprise}/settings/support`

GitHub Support の設定（サポートエンタイトルメント等）。

---

[^1]: [GitHub Docs: Configuring user display names](https://docs.github.com/enterprise-cloud@latest/admin/managing-your-enterprise-account/configuring-user-display-names-for-your-enterprise)
[^2]: [GitHub Docs: About authentication security](https://docs.github.com/enterprise-cloud@latest/admin/configuration/configuring-your-enterprise/restricting-network-traffic-to-your-enterprise-with-an-ip-allow-list)
[^3]: [GitHub Docs: Restricting network traffic with an IP allow list](https://docs.github.com/admin/configuring-settings/hardening-security-for-your-enterprise/restricting-network-traffic-to-your-enterprise-with-an-ip-allow-list)
[^4]: [GitHub Docs: About GitHub Advanced Security](https://docs.github.com/enterprise-cloud@latest/get-started/learning-about-github/about-github-advanced-security)
[^5]: [GitHub Docs: Verifying or approving a domain for your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/configuration/configuring-your-enterprise/verifying-or-approving-a-domain-for-your-enterprise)
[^6]: [GitHub Docs: About the audit log for your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/monitoring-activity-in-your-enterprise/reviewing-audit-logs-for-your-enterprise/about-the-audit-log-for-your-enterprise)
[^7]: [GitHub Docs: About Azure private networking for GitHub-hosted runners](https://docs.github.com/enterprise-cloud@latest/admin/configuring-settings/configuring-private-networking-for-hosted-compute-products/about-azure-private-networking-for-github-hosted-runners-in-your-enterprise)
