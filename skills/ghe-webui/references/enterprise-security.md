# Enterprise Security and quality

> パス: `/enterprises/{enterprise}/security/overview`

## 概要

Enterprise 全体のセキュリティアラートのトレンド、リスク分析、セキュリティ機能のカバレッジ、各種セキュリティ機能の有効化状況を一元的に確認するダッシュボード。[^1]

## ナビゲーション

| 項目 | パス |
|------|------|
| Overview | `/enterprises/{enterprise}/security/overview` |
| Risk | `/enterprises/{enterprise}/security/risk` |
| Coverage | `/enterprises/{enterprise}/security/coverage` |
| Insights > Enablement | `/enterprises/{enterprise}/security/metrics/enablement` |
| Insights > CodeQL pull requests | `/enterprises/{enterprise}/security/metrics/codeql` |
| Insights > Secret scanning | `/enterprises/{enterprise}/security/metrics/secret-scanning` |
| Findings > Dependabot > Malware | `/enterprises/{enterprise}/security/alerts/malware` |
| Findings > Dependabot > Vulnerabilities | `/enterprises/{enterprise}/security/alerts/dependabot` |
| Findings > Code scanning | `/enterprises/{enterprise}/security/alerts/code-scanning` |
| Findings > Secret scanning | `/enterprises/{enterprise}/security/alerts/secret-scanning` |
| Dismissal requests > Dependabot | `/enterprises/{enterprise}/security/dismissal-requests/dependabot` |
| Dismissal requests > Code scanning | `/enterprises/{enterprise}/security/dismissal-requests/code-scanning` |
| Dismissal requests > Secret scanning | `/enterprises/{enterprise}/security/dismissal-requests/secret-scanning` |
| Dismissal requests > Push protection bypass | `/enterprises/{enterprise}/security/bypass-requests/secret-scanning` |

## Overview

> パス: `/enterprises/{enterprise}/security/overview`

Enterprise 全体のセキュリティアラートのトレンドと分析。[^2]

- フィルタ: Advanced filter（`archived:false tool:github` 等のクエリ構文）
- 期間選択: 「Choose period...」ドロップダウン（Last 30 days 等）
- CSV Export 可能
- タブ: Detection / Remediation / Prevention

### Detection タブ

- Open alerts over time（Group by: Severity）
- Age of alerts — オープンアラートの平均経過日数
- Reopened alerts — 期間中に再オープンされたアラート数
- Secrets bypassed — プッシュ保護でバイパスされたシークレット数（View details リンクで Secret scanning metrics へ遷移）
- Impact analysis — セキュリティ影響の大きいリポジトリ・脆弱性のトップ10
  - サブタブ: Repositories / Advisories / SAST vulnerabilities

### Remediation タブ

- Closed alerts over time（Group by: Severity）
- Mean time to remediate — クローズされたアラートの平均処理日数（false positive を除く）
- Net resolve rate — 新規作成アラートに対するクローズアラートの割合（%）
- Alerts fixed with autofix suggestions — Autofix が提案されたアラートのうち採用されたものの数
- Alert activity — 期間中の新規作成・クローズ・ネットアクティビティの推移チャート

### Prevention タブ

- Prevented vs. Introduced — PR で防止されたアラートと導入されたアラートの比較
- CodeQL alerts fixed in pull requests — メインブランチへのマージ前に PR で修正された CodeQL 脆弱性の数（View CodeQL report リンクで CodeQL pull requests metrics へ遷移）
- CodeQL pull request alerts fixed with autofix suggestions — Autofix が提案された CodeQL PR アラートのうち採用されたものの数

## Risk

> パス: `/enterprises/{enterprise}/security/risk`

リポジトリ別のセキュリティリスク分析。アラートの重大度別分布とリポジトリ一覧。[^3]

- フィルタ: テキスト検索（`archived:false` 等のクエリ構文）
- Teams フィルタ
- CSV Export 可能
- ソート: Recently updated 等
- サマリーカード（Dependabot / Code scanning / Secret scanning ごと）:
  - Repositories — affected / unaffected の数
  - Open alerts — オープンアラート数（重大度別内訳リンク付き）
- リポジトリ一覧: Active / Archived 切り替え、各リポジトリのセキュリティページへのリンク

## Coverage

> パス: `/enterprises/{enterprise}/security/coverage`

セキュリティ機能の有効化カバレッジ状況。リポジトリ別のセキュリティ機能有効状態の確認。[^4]

- フィルタ: テキスト検索（`archived:false` 等のクエリ構文）
- Teams フィルタ
- CSV Export 可能
- ソート: Recently updated 等
- サマリーカード:
  - Dependabot — Alerts / Security updates の enabled / not enabled 数
  - Code scanning — Alerts / Pull request alerts の enabled / not enabled 数
  - Secret scanning — Alerts / Push protection の enabled / not enabled 数
- リポジトリ一覧: Active / Archived 切り替え、各リポジトリの Dependabot / Code scanning / Secret scanning の有効化状態を表示

## Insights > Enablement

> パス: `/enterprises/{enterprise}/security/metrics/enablement`

セキュリティ機能の有効化トレンドをタイムライン上で確認。[^4]

- フィルタ: Advanced filter（`archived:false` 等のクエリ構文）
- 期間選択: 「Choose period...」ドロップダウン（Last 30 days 等）
- タブ: Dependabot / Code scanning / Secret scanning
  - Dependabot: Dependabot と Security updates の有効化率推移チャート + データテーブル
  - Code scanning: Code scanning の有効化率推移（同様の構成）
  - Secret scanning: Secret scanning の有効化率推移（同様の構成）
- Customization settings ボタン

## Insights > CodeQL pull requests

> パス: `/enterprises/{enterprise}/security/metrics/codeql`

CodeQL による PR 分析のメトリクス。保護ブランチにマージされた PR で検出・修正された脆弱性のレポート。[^5]

- フィルタ: Advanced filter（`archived:false` 等のクエリ構文）
- 期間選択: 「Choose period...」ドロップダウン（Last 90 days 等）
- CSV Export 可能
- サマリーカード:
  - Alerts found — PR で検出された CodeQL アラートの総数
  - Copilot Autofix suggestions — Autofix 提案があったアラートの割合
  - Alerts fixed — PR で修正されたアラートの割合
- Alerts in pull requests — アラート数の推移チャート（Group by: State）
- Alerts fixed with autofix suggestions — Autofix 提案のうち採用されたものの数
- Remediation rates — Autofix あり/なしのアラート修復率比較チャート

## Insights > Secret scanning

> パス: `/enterprises/{enterprise}/security/metrics/secret-scanning`

シークレットスキャンのプッシュ保護メトリクス。バイパスされたシークレットやブロックの分析。[^6]

- フィルタ: Advanced filter
- 期間選択: 「Choose period...」ドロップダウン（Last 30 days 等）
- **Push protection**:
  - Bypassed secrets — バイパスされたシークレット数とブロック成功数
  - Bypass requests — バイパスリクエスト数（open / approved / rejected / cancelled の内訳）
  - Mean time to response — バイパスリクエストへの平均応答時間
- **Blocks**（プッシュされたすべてのシークレット。バイパスされたもの + ブロック時に修正されたものを含む）:
  - Most blocked secret types — ブロックされたシークレット種類のランキング
  - Repositories with most pushes blocked — ブロックが多いリポジトリのランキング
- **Bypasses**（プッシュ時にバイパスされ、リポジトリに露出したシークレット）:
  - Most bypassed secret types — バイパスされたシークレット種類のランキング
  - Repositories with most secrets bypassed — バイパスが多いリポジトリのランキング
  - Bypass reason distribution — バイパス理由の分布

## Findings > Dependabot > Malware

> パス: `/enterprises/{enterprise}/security/alerts/malware`

Dependabot が検出したマルウェアアラートの一覧。（Preview 機能）

- テキスト検索（`is:open` 等のクエリ構文）
- Teams フィルタ
- Open / Closed タブ切り替え
- フィルタ: Organization / Repository / Package / Ecosystem / Severity / Sort

## Findings > Dependabot > Vulnerabilities

> パス: `/enterprises/{enterprise}/security/alerts/dependabot`

Dependabot が検出した依存関係の脆弱性アラートの一覧。

- テキスト検索（`is:open` 等のクエリ構文）
- Teams フィルタ
- Open / Closed タブ切り替え
- フィルタ: Organization / Repository / Package / Ecosystem / Severity / Sort

## Findings > Code scanning

> パス: `/enterprises/{enterprise}/security/alerts/code-scanning`

Code scanning アラートの一覧。

- テキスト検索（`is:open` 等のクエリ構文）
- Teams フィルタ
- Open / Closed タブ切り替え
- フィルタ: Organization / Repository / Tool / Rule / Severity / Sort

## Findings > Secret scanning

> パス: `/enterprises/{enterprise}/security/alerts/secret-scanning`

Secret scanning アラートの一覧。

- テキスト検索（`is:open results:default` 等のクエリ構文、Filters プリセットボタン付き）
- Teams フィルタ
- Open / Closed タブ切り替え
- フィルタ: Validity / Owner / Repository / Secret type / Sort

## Dismissal requests > Dependabot / Code scanning / Secret scanning

> パス: `/enterprises/{enterprise}/security/dismissal-requests/{dependabot|code-scanning|secret-scanning}`

アラートの却下リクエストの一覧と管理。Enterprise 全体の却下リクエストを確認できる。[^7]

- フィルタ: All organizations / All approvers / All requesters / 期間（Last week 等） / All statuses

## Dismissal requests > Push protection bypass

> パス: `/enterprises/{enterprise}/security/bypass-requests/secret-scanning`

プッシュ保護のバイパスリクエストの一覧と管理。Delegated bypass が有効な場合に、バイパスリクエストを確認・承認・拒否できる。[^8]

- フィルタ: All organizations / All approvers / All requesters / 期間（Last week 等） / All statuses
- 「Learn more about delegated bypass」ドキュメントリンク付き

---

[^1]: [GitHub Docs: About security overview](https://docs.github.com/enterprise-cloud@latest/code-security/concepts/security-at-scale/about-security-overview)
[^2]: [GitHub Docs: Viewing security insights](https://docs.github.com/enterprise-cloud@latest/code-security/security-overview/viewing-security-insights)
[^3]: [GitHub Docs: Assessing the security risk of your code](https://docs.github.com/enterprise-cloud@latest/code-security/security-overview/assessing-code-security-risk)
[^4]: [GitHub Docs: Assessing adoption of security features](https://docs.github.com/enterprise-cloud@latest/code-security/security-overview/assessing-adoption-code-security)
[^5]: [GitHub Docs: Viewing metrics for pull request alerts](https://docs.github.com/enterprise-cloud@latest/code-security/security-overview/viewing-metrics-for-pull-request-alerts)
[^6]: [GitHub Docs: Viewing metrics for secret scanning push protection](https://docs.github.com/enterprise-cloud@latest/code-security/security-overview/viewing-metrics-for-secret-scanning-push-protection)
[^7]: [GitHub Docs: Reviewing requests to bypass push protection](https://docs.github.com/enterprise-cloud@latest/code-security/security-overview/reviewing-requests-to-bypass-push-protection)
[^8]: [GitHub Docs: About delegated bypass for push protection](https://docs.github.com/enterprise-cloud@latest/code-security/concepts/secret-security/about-delegated-bypass-for-push-protection)
