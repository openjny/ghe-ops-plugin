# Enterprise Organizations

> パス: `/enterprises/{enterprise}/organizations`

## 概要

Enterprise に所属する Organization の一覧管理。Org の作成、検索、フィルタリング、Custom Properties の管理を行う。

## ナビゲーション

| 項目 | パス |
|------|------|
| Overview | `/enterprises/{enterprise}/organizations` |
| Custom Properties | `/enterprises/{enterprise}/settings/org-custom-properties` |

## Overview

> パス: `/enterprises/{enterprise}/organizations`

Organization の一覧管理。

- Org 一覧: 名前、自分のロール、2FA 状態、メンバー数、リポジトリ数、デプロイキー数
- 検索: 「Find an organization…」
- フィルタ: Two-factor authentication, Deploy keys, Your role
- アクション: 「New organization」で Org 新規作成
- Org ごとのコンテキストメニュー: Organization menu

## Custom Properties

> パス: `/enterprises/{enterprise}/settings/org-custom-properties`

Enterprise レベルで Organization に付与するカスタムプロパティの定義・管理。[^2]

- 概要テキスト: カスタムプロパティを使用してコンプライアンスフレームワーク・データの機密性・プロジェクト詳細などの情報を Organization に付与できる
- タブ: Properties / Set values
- Properties タブ: カスタムプロパティスキーマの定義・管理
  - 「New property」で新規プロパティ作成
  - プロパティ検索・フィルタ
  - プロパティ定義項目: 名前、説明、タイプ、Organization アクターによる設定許可、全 Organization への必須化（デフォルト値付き）
- Set values タブ: Organization を選択してプロパティ値を一括設定

---

[^1]: [GitHub Docs: Managing organizations in your enterprise](https://docs.github.com/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-organizations-in-your-enterprise)
[^2]: [GitHub Docs: Managing custom properties for organizations](https://docs.github.com/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-organizations-in-your-enterprise/managing-custom-properties-for-organizations)
