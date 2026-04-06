# Enterprise Identity Provider

> パス: `/enterprises/{enterprise}/settings/single_sign_on_configuration`

## 概要

Enterprise の ID プロバイダー（IdP）連携設定。OIDC または SAML による SSO 認証を構成する。EMU（Enterprise Managed Users）環境では IdP がユーザーのライフサイクルを管理する。[^1]

## サイドナビゲーション

| 項目 | パス |
|------|------|
| Single sign-on configuration | `/enterprises/{enterprise}/settings/single_sign_on_configuration` |
| Groups | `/enterprises/{enterprise}/external_groups` |

## セクション: Single sign-on configuration

### OIDC single sign-on

| 項目 | 説明 | 選択肢・デフォルト |
|------|------|-------------------|
| OIDC single sign-on | OIDC SSO の有効/無効 | On / Off トグル |
| Tenant ID | IdP のテナント ID（Entra ID） | テキスト（無効時は読み取り専用） |

- 対応 IdP: Microsoft Entra ID（旧 Azure AD）[^2]
- Recovery codes のリンク: `/enterprises/{enterprise}/settings/oidc_provider/recovery_codes`
- SSO URL: `/enterprises/{enterprise}/sso`
- 注意: OIDC の無効化は setup user でログインした場合のみ可能

### SAML single sign-on

| 項目 | 説明 |
|------|------|
| Switch to SAML | OIDC から SAML に切り替えるボタン |

- 対応 IdP: Azure, Okta, OneLogin, Ping Identity, カスタム SAML 2.0[^3]

### Single sign-on settings

| 項目 | 説明 | 選択肢・デフォルト |
|------|------|-------------------|
| Automatically redirect users to sign in | Enterprise リソースへの訪問時に IdP へ自動リダイレクト | On / Off トグル（デフォルト: Off） |

### Danger zone

| 項目 | 説明 |
|------|------|
| Single sign-on lockdown | SSO 経由の認証をすべてブロック（Enterprise owner を除く） |

## セクション: Groups

> パス: `/enterprises/{enterprise}/external_groups`

IdP から同期されたグループの一覧。SCIM プロビジョニングで管理される。[^4]

---

[^1]: [GitHub Docs: About enterprise managed users](https://docs.github.com/enterprise-cloud@latest/admin/managing-iam/understanding-iam-for-enterprises/about-enterprise-managed-users)
[^2]: [GitHub Docs: Configuring OIDC for Enterprise Managed Users](https://docs.github.com/admin/managing-iam/configuring-authentication-for-enterprise-managed-users/configuring-oidc-for-enterprise-managed-users)
[^3]: [GitHub Docs: Configuring SAML single sign-on for your enterprise](https://docs.github.com/admin/managing-iam/using-saml-for-enterprise-iam/configuring-saml-single-sign-on-for-your-enterprise)
[^4]: [GitHub Docs: Managing team memberships with identity provider groups](https://docs.github.com/enterprise-cloud@latest/admin/managing-iam/provisioning-user-accounts-with-scim/managing-team-memberships-with-identity-provider-groups)
