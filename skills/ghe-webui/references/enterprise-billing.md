# Enterprise Billing and licensing

> パス: `/enterprises/{enterprise}/billing`

## 概要

Enterprise の課金管理。メータード使用量、ライセンス、コストセンター、バジェット、支払い情報などを管理する。[^1]

## ナビゲーション

| 項目 | パス |
|------|------|
| Overview | `/enterprises/{enterprise}/billing` |
| Usage > Metered usage | `/enterprises/{enterprise}/billing/usage` |
| Usage > Premium request analytics | `/enterprises/{enterprise}/billing/premium_requests_usage` |
| Licensing | `/enterprises/{enterprise}/licensing` |
| Cost centers | `/enterprises/{enterprise}/billing/cost_centers` |
| Budgets and alerts | `/enterprises/{enterprise}/billing/budgets` |
| Payment information | `/enterprises/{enterprise}/billing/payment_information` |
| Payment history | `/enterprises/{enterprise}/billing/payment_history` |
| Billing contacts | `/enterprises/{enterprise}/billing/contacts` |
| Marketplace apps | `/enterprises/{enterprise}/billing/marketplace_apps` |
| Sponsorships | `/enterprises/{enterprise}/billing/sponsorships` |

> Usage は展開可能なサブメニューで、Metered usage と Premium request analytics の 2 項目を含む。

## Overview

> パス: `/enterprises/{enterprise}/billing`

Enterprise の課金概要。

- Current metered usage: 当月のグロスメータード使用量
- Current included usage: 当月の含まれる使用量割引
- Past due: 未払い額
- Next payment: 次回支払い予定日（Azure 経由の場合はその旨を表示）
- Metered usage: 期間別使用量グラフ（Timeframe ドロップダウンで期間選択）
- Usage by products: 製品別の使用量内訳（Copilot / Actions / Codespaces / Advanced Security / Enterprise / Git LFS / Packages / Spark）
  - 各製品タブに使用量サマリー、View details リンク、Manage リンクを表示
  - Copilot タブ: Copilot usage（使用額）、Billable licenses（課金対象ライセンス数）、Copilot premium requests（追加プレミアムリクエスト費用）
- Usage by organization / Usage by repository: 組織・リポジトリ別の使用量内訳

## Metered usage

> パス: `/enterprises/{enterprise}/billing/usage`

全サービスを横断したメータード使用量の詳細ビュー。[^2]

- Get usage report: 使用量レポートの取得（メールで送信）[^3]
- フィルター: 検索ボックスで製品・Org・リポジトリ等を絞り込み
- Group by: グルーピング条件の選択（None / 各種フィルター軸）
- Timeframe: 期間選択（Current month 等）
- Metered usage チャート: フィルターに応じた使用量の時系列グラフ
- Usage breakdown テーブル: 日付・Gross amount・Billed amount の明細

## Premium request analytics

> パス: `/enterprises/{enterprise}/billing/premium_requests_usage`

Copilot プレミアムリクエストの使用量分析ビュー。[^2]

- Get usage report: プレミアムリクエスト使用量レポートの取得[^3]
- フィルター: 検索ボックスで絞り込み
- Group by: グルーピング条件の選択（Models / Organizations / Users 等）
- Timeframe: 期間選択
- Total billed amount: プレミアムリクエストの課金総額
- Billed premium requests: 含まれる使用量を超えた課金対象リクエスト数
- Included premium requests consumed: ライセンスに含まれるプレミアムリクエストの消費状況（月次リセット日を表示）
- Usage grouped by ... チャート: グルーピング条件に応じた使用量グラフ
- Usage breakdown テーブル: 使用量の明細

## Licensing

> パス: `/enterprises/{enterprise}/licensing`

ライセンスの割り当てと消費状況。製品ごとにセクションが分かれる。

- **Enterprise Cloud**: Consumed licenses（消費ライセンス数）、Estimated monthly payment（推定月額）、CSV レポートダウンロード、Manage リンク
- **Advanced Security**: Consumed licenses（Secret Protection / Code Security 別の内訳）、Estimated monthly payment、CSV レポートダウンロード、Manage ボタン
- **Copilot**: Consumed licenses（Business / Enterprise ライセンス別の内訳）、Estimated monthly payment、Activity report の取得、Manage リンク
- **Enterprise Server**: サーバーライセンスの管理
- **Enterprise Server keys**: サーバーキーの生成
- **Enterprise Server instances**: サーバーインスタンスの追加・管理（Add server usage ボタン）

## Cost centers

> パス: `/enterprises/{enterprise}/billing/cost_centers`

コストセンターを作成し、Org・リポジトリ・ユーザーを割り当ててメータード使用量を分類。Azure サブスクリプションとの紐付けも可能。[^4]

- Active / Deleted タブ: アクティブなコストセンターと削除済みコストセンターを切り替え
- コストセンター一覧テーブル

## Budgets and alerts

> パス: `/enterprises/{enterprise}/billing/budgets`

使用量のバジェットとアラートの設定。製品・SKU ごとに月次使用量上限を設定し、支出を管理。[^5]

- Included usage alerts: On/Off トグル（プラン含有使用量が 90%・100% に達した際のメール通知）
- New budget: 新規バジェット作成リンク
- Enterprise budgets テーブル: Enterprise レベルのバジェット一覧
- Budgets テーブル: その他のバジェット一覧

## Payment information

> パス: `/enterprises/{enterprise}/billing/payment_information`

支払い方法の管理。[^6]

- Billing Cycle: 課金サイクル（月次）と次回請求日の表示
- Azure subscription: Azure サブスクリプションの接続・編集・削除。メータード課金を Azure 経由で管理する

## Payment history

> パス: `/enterprises/{enterprise}/billing/payment_history`

過去の支払い履歴の確認。請求書のダウンロード。

## Billing contacts

> パス: `/enterprises/{enterprise}/billing/contacts`

課金通知（支払い通知およびバジェット閾値アラート）の送信先メールアドレスの管理。Primary メールアドレスの編集、追加メールアドレスの登録が可能。

## Marketplace apps

> パス: `/enterprises/{enterprise}/billing/marketplace_apps`

GitHub Marketplace アプリの課金管理。

## Sponsorships

> パス: `/enterprises/{enterprise}/billing/sponsorships`

GitHub Sponsors の課金管理。

---

[^1]: [GitHub Docs: Introduction to billing and licensing](https://docs.github.com/enterprise-cloud@latest/billing/get-started/introduction-to-billing)
[^2]: [GitHub Docs: Viewing your usage of metered products and licenses](https://docs.github.com/enterprise-cloud@latest/billing/how-tos/products/view-product-use)
[^3]: [GitHub Docs: Billing reports reference](https://docs.github.com/enterprise-cloud@latest/billing/reference/usage-reports)
[^4]: [GitHub Docs: Using cost centers to allocate costs to business units](https://docs.github.com/enterprise-cloud@latest/billing/tutorials/use-cost-centers)
[^5]: [GitHub Docs: Budgets and alerts](https://docs.github.com/enterprise-cloud@latest/billing/concepts/budgets-and-alerts)
[^6]: [GitHub Docs: Connecting an Azure subscription](https://docs.github.com/enterprise-cloud@latest/billing/how-tos/set-up-payment/connect-azure-sub)
