# Enterprise Identity Provider

> パス: `/enterprises/{enterprise}/settings/single_sign_on_configuration`

## 概要

Enterprise の ID プロバイダー（IdP）連携設定。OIDC または SAML による SSO 認証を構成する。EMU（Enterprise Managed Users）環境では IdP がユーザーのライフサイクルを管理する。[^1]

## ナビゲーション

| 項目 | パス |
|------|------|
| Single sign-on configuration | `/enterprises/{enterprise}/settings/single_sign_on_configuration` |
| Groups | `/enterprises/{enterprise}/external_groups` |

## Single sign-on configuration

> パス: `/enterprises/{enterprise}/settings/single_sign_on_configuration`

### OIDC single sign-on

- OIDC single sign-on: OIDC SSO の有効/無効（選択肢: On / Off トグル）
- Tenant ID: IdP のテナント ID（Entra ID）（テキスト、無効時は読み取り専用）

- 対応 IdP: Microsoft Entra ID（旧 Azure AD）[^2]
- Recovery codes のリンク: `/enterprises/{enterprise}/settings/oidc_provider/recovery_codes`
- SSO URL: `/enterprises/{enterprise}/sso`
- 注意: OIDC の無効化は setup user でログインした場合のみ可能

### SAML single sign-on

- Switch to SAML: OIDC から SAML に切り替えるボタン

- 対応 IdP: Azure, Okta, OneLogin, Ping Identity, カスタム SAML 2.0[^3]

### Single sign-on settings

- Automatically redirect users to sign in: Enterprise リソースへの訪問時に IdP へ自動リダイレクト（選択肢: On / Off トグル、デフォルト: Off）

### Danger zone

- Single sign-on lockdown: SSO 経由の認証をすべてブロック（Enterprise owner を除く）

## Groups

> パス: `/enterprises/{enterprise}/external_groups`

IdP から同期されたグループの一覧。SCIM プロビジョニングにより IdP からグループメンバーシップ情報が GitHub に同期され、リンクされた GitHub チームのメンバーが自動更新される。グループやメンバーシップの編集は IdP 側で行う。[^4]

- グループ検索: 名前でグループを検索
- Sync status フィルター: 同期ステータスでフィルタリング
- Sort: グループ一覧のソート

- 各グループにはリンク済みチーム数とメンバー数が表示される
- グループ名をクリックすると、メンバー一覧とリンク済みチームを確認できる（パス: `/enterprises/{enterprise}/external_group_members/{id}`）

---

[^1]: [GitHub Docs: About enterprise managed users](https://docs.github.com/enterprise-cloud@latest/admin/concepts/identity-and-access-management/enterprise-managed-users)
[^2]: [GitHub Docs: Configuring OIDC for Enterprise Managed Users](https://docs.github.com/admin/managing-iam/configuring-authentication-for-enterprise-managed-users/configuring-oidc-for-enterprise-managed-users)
[^3]: [GitHub Docs: Configuring SAML single sign-on for your enterprise](https://docs.github.com/admin/managing-iam/using-saml-for-enterprise-iam/configuring-saml-single-sign-on-for-your-enterprise)
[^4]: [GitHub Docs: Managing team memberships with identity provider groups](https://docs.github.com/enterprise-cloud@latest/admin/managing-iam/provisioning-user-accounts-with-scim/managing-team-memberships-with-identity-provider-groups)
