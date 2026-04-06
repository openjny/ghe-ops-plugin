# Enterprise Billing and licensing

> パス: `/enterprises/{enterprise}/billing`

## 概要

Enterprise の課金管理。メータード使用量、ライセンス、コストセンター、バジェット、支払い情報などを管理する。[^1]

## サイドナビゲーション

| 項目 | パス |
|------|------|
| Overview | `/enterprises/{enterprise}/billing` |
| Usage | (展開可能なサブメニュー) |
| Licensing | `/enterprises/{enterprise}/licensing` |
| Cost centers | `/enterprises/{enterprise}/billing/cost_centers` |
| Budgets and alerts | `/enterprises/{enterprise}/billing/budgets` |
| Payment information | `/enterprises/{enterprise}/billing/payment_information` |
| Payment history | `/enterprises/{enterprise}/billing/payment_history` |
| Billing contacts | `/enterprises/{enterprise}/billing/contacts` |
| Marketplace apps | `/enterprises/{enterprise}/billing/marketplace_apps` |
| Sponsorships | `/enterprises/{enterprise}/billing/sponsorships` |

## セクション: Overview

### 内容

| 項目 | 説明 |
|------|------|
| Current metered usage | 当月のグロスメータード使用量 |
| Current included usage | 当月の含まれる使用量割引 |
| Past due | 未払い額 |
| Next payment | 次回支払い予定日 |
| Metered usage | 期間別使用量グラフ |

### UI 要素

- 期間選択: Timeframe ドロップダウン（Current month 等）
- 詳細リンク: 各項目の「More details」/ 「Payment history」リンク

## セクション: Licensing

> パス: `/enterprises/{enterprise}/licensing`

ライセンスの割り当てと消費状況。

## セクション: Cost centers

> パス: `/enterprises/{enterprise}/billing/cost_centers`

コストセンターを作成し、Org やチームを割り当てて使用量を分類。[^2]

## セクション: Budgets and alerts

> パス: `/enterprises/{enterprise}/billing/budgets`

使用量のバジェットとアラートの設定。Premium Requests 等の支出上限を管理。

---

[^1]: [GitHub Docs: About billing for your enterprise](https://docs.github.com/enterprise-cloud@latest/billing/managing-your-github-billing-settings/about-billing-for-your-enterprise)
[^2]: [GitHub Docs: Managing cost centers for your enterprise](https://docs.github.com/enterprise-cloud@latest/billing/using-the-new-billing-platform/managing-your-payment-and-billing-information/managing-cost-centers-for-your-enterprise)
