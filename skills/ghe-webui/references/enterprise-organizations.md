# Enterprise Organizations

> パス: `/enterprises/{enterprise}/organizations`

## 概要

Enterprise に所属する Organization の一覧管理。Org の作成、検索、フィルタリング、Custom Properties の管理を行う。

## サブナビゲーション

| 項目 | パス |
|------|------|
| Overview | `/enterprises/{enterprise}/organizations` |
| Custom Properties | `/enterprises/{enterprise}/settings/org-custom-properties` |

## セクション: Overview

Organization の一覧管理。

- Org 一覧: 名前、自分のロール、2FA 状態、メンバー数、リポジトリ数、デプロイキー数
- 検索: 「Find an organization…」
- フィルタ: Two-factor authentication, Deploy keys, Your role
- アクション: 「New organization」で Org 新規作成

## セクション: Custom Properties

> パス: `/enterprises/{enterprise}/settings/org-custom-properties`

Enterprise レベルで Organization に付与するカスタムプロパティの定義・管理。

---

[^1]: [GitHub Docs: Managing organizations in your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-organizations-in-your-enterprise)
[^2]: [GitHub Docs: Managing custom properties for organizations](https://docs.github.com/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-organizations-in-your-enterprise/managing-custom-properties-for-organizations-in-your-enterprise)
