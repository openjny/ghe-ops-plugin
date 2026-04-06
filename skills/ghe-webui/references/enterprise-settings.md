# Enterprise Settings

> パス: `/enterprises/{enterprise}/settings/profile`

## 概要

Enterprise の一般設定、認証セキュリティ、セキュリティ機能構成、ドメイン管理、Audit ログ、Webhook、ネットワーク構成、GitHub Apps、アナウンスメント、サポート設定を管理する。

## ナビゲーション

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

## General

> パス: `/enterprises/{enterprise}/settings/profile`

Enterprise のプロフィール情報、外観、フッター、削除を管理する。

### Profile

- Enterprise の表示名、説明、Web サイト URL、所在地、セキュリティ連絡先メールを設定できる
- プロフィール画像をアップロードできる
- Hosting region と Enterprise URL の表示（読み取り専用）

### Member appearance

- Profile name visibility: メンバーのプロフィール名をハンドルと一緒に表示するか（Let organizations decide / Enabled / Disabled）[^1]

### Custom footer

- Enterprise 全体のフッターにカスタムリンクを追加（最大5つ、タイトルと URL のペア）

### Danger zone

- Enterprise の削除（すべての Organization を先に削除する必要がある）

## Authentication security

> パス: `/enterprises/{enterprise}/settings/security`

認証に関するセキュリティ設定。[^2]

- SSH certificate authorities: SSH 証明書認証局の登録・管理
- IP allow list: IP アドレスベースのアクセス制限（Enabled / Disabled）[^3]
- Credentials: Enterprise 内の認証情報の概要と管理
  - Fine-grained personal access tokens の一覧
  - Personal access tokens (classic) の一覧
  - SSH keys の一覧
  - GitHub App / OAuth app user access tokens の一覧
- Danger zone: SSO 認証の一括取り消し、トークン・キーの一括削除

## Advanced Security

> パス: `/enterprises/{enterprise}/settings/security_analysis`

GitHub Advanced Security（GHAS）の構成管理。Policies の Advanced Security とは別ページ。[^4]

- カバレッジ状況: Dependabot、Code Security、Secret Protection の保護率
- Configurations: セキュリティ構成の作成・管理（「GitHub recommended」等のプリセット含む）
- Additional Settings:
  - Secret Protection: push protection のパターン設定、リソースリンク設定
  - User namespace repositories:
    - GitHub Secret Protection for user namespace repositories（Enable all / Disable all）
    - Automatically enable secret scanning for new user namespace repositories（On / Off）
    - Automatically enable push protection for new user namespace repositories（On / Off）

## Verified & approved domains

> パス: `/enterprises/{enterprise}/settings/domains`

Enterprise のドメイン検証と承認。メール通知やプロフィールの URL 検証に使用。[^5]

## Audit log

> パス: `/enterprises/{enterprise}/settings/audit-log`

Enterprise の監査ログ。3つのタブで構成される。[^6]

### Events

- 監査イベントの検索・フィルタ・閲覧
- エクスポート（JSON / CSV）、Git Events のエクスポート

### Log streaming

- 外部データ管理システムへの監査ログストリーミングの設定（Amazon S3、Azure Blob Storage、Azure Event Hubs、Datadog、Google Cloud Storage、Splunk）[^8]

### Settings

- Disclose actor IP addresses in audit logs: ソース IP アドレスの開示（Enable source IP disclosure）[^9]
- API Requests: API リクエストイベントのストリーミング有効化（Enable API Request Events）。保持期間は24時間

## Retired namespaces

> パス: `/enterprises/{enterprise}/settings/retired_namespaces`

名前変更や削除された Org・ユーザーの旧名前空間の管理。リタイアされた名前空間の一覧と復元操作。

## Hooks

> パス: `/enterprises/{enterprise}/settings/hooks`

Enterprise 全体の Webhook の作成・管理。イベントの選択と配信先 URL の設定。

## Hosted compute networking

> パス: `/enterprises/{enterprise}/settings/network_configurations`

GitHub-hosted runners のネットワーク構成。Azure VNET への接続設定。[^7]

## GitHub Apps

> パス: `/enterprises/{enterprise}/settings/apps`

Enterprise の GitHub Apps の管理。2つのタブで構成される。

- My Apps: Enterprise が所有する GitHub App の一覧・作成（New GitHub App）
- Installed Apps（Preview）: Enterprise にインストールされた GitHub App の一覧・管理

## Announcement

> パス: `/enterprises/{enterprise}/settings/announcement`

Enterprise 全体に表示するアナウンスメントバナーの作成・管理。[^10]

- Critical message: Markdown 形式でメッセージを作成（Write / Preview タブ）
- Expiration date: 有効期限の設定（任意、指定日の UTC 0時に期限切れ）
- Allow users to dismiss the announcement: ユーザーにアナウンスメントの非表示を許可するオプション

## Support

> パス: `/enterprises/{enterprise}/settings/support`

GitHub Support portal のエンタイトルメント管理。[^11]

- 指定メンバーに Enterprise のサポートチケットの閲覧・コメント権限を付与できる
- Enterprise 管理者は自動的にエンタイトルメントを持つ
- 追加で最大20メンバーにエンタイトルメントを付与可能（Premium / Standard プラン）

---

[^1]: [GitHub Docs: Configuring user display names](https://docs.github.com/enterprise-cloud@latest/admin/managing-your-enterprise-account/configuring-user-display-names-for-your-enterprise)
[^2]: [GitHub Docs: About authentication security](https://docs.github.com/enterprise-cloud@latest/admin/configuration/configuring-your-enterprise/restricting-network-traffic-to-your-enterprise-with-an-ip-allow-list)
[^3]: [GitHub Docs: Restricting network traffic with an IP allow list](https://docs.github.com/admin/configuring-settings/hardening-security-for-your-enterprise/restricting-network-traffic-to-your-enterprise-with-an-ip-allow-list)
[^4]: [GitHub Docs: About GitHub Advanced Security](https://docs.github.com/enterprise-cloud@latest/get-started/learning-about-github/about-github-advanced-security)
[^5]: [GitHub Docs: Verifying or approving a domain for your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/configuration/configuring-your-enterprise/verifying-or-approving-a-domain-for-your-enterprise)
[^6]: [GitHub Docs: About the audit log for your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/monitoring-activity-in-your-enterprise/reviewing-audit-logs-for-your-enterprise/about-the-audit-log-for-your-enterprise)
[^7]: [GitHub Docs: About Azure private networking for GitHub-hosted runners](https://docs.github.com/enterprise-cloud@latest/admin/configuring-settings/configuring-private-networking-for-hosted-compute-products/about-azure-private-networking-for-github-hosted-runners-in-your-enterprise)
[^8]: [GitHub Docs: Streaming the audit log for your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/monitoring-activity-in-your-enterprise/reviewing-audit-logs-for-your-enterprise/streaming-the-audit-log-for-your-enterprise)
[^9]: [GitHub Docs: Displaying IP addresses in the audit log for your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/monitoring-activity-in-your-enterprise/reviewing-audit-logs-for-your-enterprise/displaying-ip-addresses-in-the-audit-log-for-your-enterprise)
[^10]: [GitHub Docs: Customizing user messages for your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/managing-accounts-and-repositories/communicating-information-to-users-in-your-enterprise/customizing-user-messages-for-your-enterprise)
[^11]: [GitHub Docs: Managing support entitlements for your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-users-in-your-enterprise/managing-support-entitlements-for-your-enterprise)
