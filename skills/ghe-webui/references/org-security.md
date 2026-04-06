# Organization Security and quality

> パス: `/orgs/{org}/security/overview`

## 概要

Organization のセキュリティ概況を一元的に可視化するダッシュボード。セキュリティアラートの検出・修復・予防のトレンド、リスク評価、セキュリティ機能の採用状況、アラートの一覧・管理、dismissal リクエストの確認ができる。GitHub Advanced Security（GitHub Secret Protection / GitHub Code Security）の機能を含む [^1]。

## ナビゲーション

| 項目 | パス |
|------|------|
| Overview | `/orgs/{org}/security/overview` |
| Risk | `/orgs/{org}/security/risk` |
| Coverage | `/orgs/{org}/security/coverage` |
| Assessments | `/orgs/{org}/security/assessments` |
| Campaigns | `/orgs/{org}/security/campaigns` |
| Insights > Enablement | `/orgs/{org}/security/metrics/enablement` |
| Insights > Code quality | `/orgs/{org}/security/quality` |
| Insights > Dependabot | `/orgs/{org}/security/metrics/dependabot` |
| Insights > CodeQL pull requests | `/orgs/{org}/security/metrics/codeql` |
| Insights > Secret scanning | `/orgs/{org}/security/metrics/secret-scanning` |
| Findings > Dependabot > Malware | `/orgs/{org}/security/alerts/malware` |
| Findings > Dependabot > Vulnerabilities | `/orgs/{org}/security/alerts/dependabot` |
| Findings > Code scanning | `/orgs/{org}/security/alerts/code-scanning` |
| Findings > Secret scanning > Default | `/orgs/{org}/security/alerts/secret-scanning` |
| Findings > Secret scanning > Generic | `/orgs/{org}/security/alerts/secret-scanning?query=is%3Aopen+results%3Ageneric` |
| Dismissal requests > Code scanning | `/orgs/{org}/security/bypass-requests/code-scanning` |
| Dismissal requests > Secret scanning | `/orgs/{org}/security/closure-requests/secret-scanning` |
| Dismissal requests > Push protection bypass | `/orgs/{org}/security/bypass-requests/secret-scanning` |

## Overview

> パス: `/orgs/{org}/security/overview`

Organization 全体のアラートトレンドとインサイトを表示するダッシュボード [^2]。

- フィルター: アーカイブ状態、ツール名等の条件で絞り込み可能
- 期間選択: 表示する期間を選択
- Export CSV: データを CSV でエクスポート
- Detection / Remediation / Prevention タブ:
  - Detection: オープンアラートの推移（Severity 別にグループ化可能）、アラートの平均経過日数、再オープンされたアラート数、シークレットバイパス数
  - Remediation: 修復に関するメトリクス
  - Prevention: 予防に関するメトリクス
- Impact analysis: リポジトリ / Advisory / SAST 脆弱性の Top 10 を表示

## Risk

> パス: `/orgs/{org}/security/risk`

Organization 全体のオープンアラート数をリポジトリ別に表示 [^3]。

- 検索・フィルター: アーカイブ状態等で絞り込み
- Teams フィルター: チーム単位で絞り込み
- Export CSV: データを CSV でエクスポート
- セキュリティツール別サマリー:
  - Dependabot: 影響を受けるリポジトリ数・オープンアラート数
  - Code scanning: 影響を受けるリポジトリ数・オープンアラート数
  - Secret scanning: 影響を受けるリポジトリ数・オープンアラート数
- リポジトリ一覧: Active / Archived タブ、ソート（Recently updated 等）

## Coverage

> パス: `/orgs/{org}/security/coverage`

Organization 全体のセキュリティ機能の採用状況を表示 [^4]。

- 検索・フィルター: アーカイブ状態等で絞り込み
- Teams フィルター: チーム単位で絞り込み
- Export CSV: データを CSV でエクスポート
- セキュリティツール別の有効化状況:
  - Dependabot: Alerts（enabled / not enabled）、Security updates（enabled / not enabled）
  - Code scanning: Alerts（enabled / not enabled）、Pull request alerts（enabled / not enabled）
  - Secret scanning: Alerts（enabled / not enabled）、Push protection（enabled / not enabled）
- リポジトリ一覧: 各リポジトリのツール別有効化状態を表示

## Assessments

> パス: `/orgs/{org}/security/assessments`

Organization のシークレットリスク評価（Secret Risk Assessment）を実行し、公開リークの監査レポートを取得する [^5]。

- Scan your organization ボタン: Organization 全体のスキャンを実行
- Learn More: GitHub Secret Protection の詳細情報へのリンク
- FAQ:
  - What happens once I start the scan?
  - How will I be notified?
  - What is the cost of a leaked secret?

## Campaigns

> パス: `/orgs/{org}/security/campaigns`

セキュリティアラートの修復を加速するためのキャンペーンを作成・管理する [^6]。

- Campaign types タブ:
  - Code: Code scanning アラートに基づくキャンペーン（Copilot Autofix による自動修正提案を含む）
  - Secrets: Secret scanning アラートに基づくキャンペーン
- キャンペーン機能: アラートのグループ化、担当者の割り当て、進捗の追跡、Copilot cloud agent への割り当て

## Insights > Enablement

> パス: `/orgs/{org}/security/metrics/enablement`

セキュリティ機能の有効化トレンドを時系列で表示 [^7]。

- フィルター: アーカイブ状態等で絞り込み
- 期間選択: 表示する期間を選択
- セキュリティツール別タブ:
  - Dependabot: Dependabot と Security updates の有効化率の推移
  - Code scanning: Code scanning の有効化率の推移
  - Secret scanning: Secret scanning の有効化率の推移
- 表示形式: ラインチャート + データテーブル

## Insights > Code quality

> パス: `/orgs/{org}/security/quality`

コード品質のモニタリング（Preview 機能）[^8]。

- リポジトリ単位で Code quality を有効化するとモニタリングを開始できる
- Organization 全体での一括有効化は今後対応予定

## Insights > Dependabot

> パス: `/orgs/{org}/security/metrics/dependabot`

Dependabot による脆弱性レポート。

- フィルター: アーカイブ状態等で絞り込み
- Alert prioritization: アラートのファネル分類（カテゴリ設定可能）
- Alerts closed in the last 30 days: 修復方法別の内訳（fixed with Dependabot / manually dismissed / auto-dismissed）
- Most vulnerabilities: 最も多くの脆弱性を持つパッケージの表示

## Insights > CodeQL pull requests

> パス: `/orgs/{org}/security/metrics/codeql`

CodeQL による PR アラートのレポート [^9]。マージ済み PR で CodeQL が検出したセキュリティ脆弱性の分析。

- フィルター: アーカイブ状態等で絞り込み
- 期間選択: 表示する期間を選択（デフォルト: Last 90 days）
- Export CSV: データを CSV でエクスポート
- Alerts found: PR でマージされたアラートの総数
- Copilot Autofix suggestions: Autofix 提案が生成されたアラートの割合
- Alerts fixed: PR で検出されたアラートの修復率
- Alerts in pull requests: PR アラートの推移（State 別にグループ化可能）
- Alerts fixed with autofix suggestions: Autofix が受け入れられたアラートの数
- Remediation rates: Autofix あり / なしの修復率の比較チャート
- Mean time to remediate: Autofix あり / なしの平均修復時間の比較チャート

## Insights > Secret scanning

> パス: `/orgs/{org}/security/metrics/secret-scanning`

Secret scanning の Push protection メトリクスを表示 [^10]。

- フィルター: 絞り込み条件を指定
- 期間選択: 表示する期間を選択（デフォルト: Last 30 days）
- Push protection:
  - Bypassed secrets: バイパスされたシークレット数 / 総検出数
  - Bypass requests: バイパスリクエスト数とステータス別内訳（open / approved / rejected / cancelled）
  - Mean time to response: バイパスリクエストへの平均応答時間
- Blocks: プッシュでブロックされたシークレットの分析
  - Most blocked secret types: 最も多くブロックされたシークレットタイプ
  - Repositories with most pushes blocked: プッシュが最もブロックされたリポジトリ
- Bypasses: バイパスされたシークレットの分析
  - Most bypassed secret types: 最も多くバイパスされたシークレットタイプ
  - Repositories with most secrets bypassed: シークレットが最もバイパスされたリポジトリ
  - Bypass reason distribution: バイパス理由の分布

## Findings > Dependabot > Malware

> パス: `/orgs/{org}/security/alerts/malware`

Dependabot が検出したマルウェアアラートの一覧（Preview 機能）。

- 検索: アラートの検索
- Teams フィルター: チーム単位で絞り込み
- ステータス: Open / Closed タブ
- フィルター: Repository、Package、Ecosystem、Severity、Sort

## Findings > Dependabot > Vulnerabilities

> パス: `/orgs/{org}/security/alerts/dependabot`

Dependabot が検出した脆弱性アラートの一覧 [^11]。

- 検索: アラートの検索
- Teams フィルター: チーム単位で絞り込み
- ステータス: Open / Closed タブ
- フィルター: Repository、Package、Ecosystem、Severity、Sort

## Findings > Code scanning

> パス: `/orgs/{org}/security/alerts/code-scanning`

Code scanning が検出したアラートの一覧 [^12]。

- Code scanning が未有効の場合、有効化を促すメッセージと設定ページへのリンクを表示

## Findings > Secret scanning > Default

> パス: `/orgs/{org}/security/alerts/secret-scanning`

Secret scanning が検出したアラートの一覧（デフォルトパターン）[^13]。

- Secret scanning が未有効の場合、有効化を促すメッセージとセキュリティ設定ページへのリンクを表示

## Findings > Secret scanning > Generic

> パス: `/orgs/{org}/security/alerts/secret-scanning?query=is%3Aopen+results%3Ageneric`

Secret scanning が AI を使って検出したジェネリックシークレットのアラート一覧 [^14]。

## Dismissal requests > Code scanning

> パス: `/orgs/{org}/security/bypass-requests/code-scanning`

Code scanning アラートの dismissal リクエストを Organization 横断で表示・管理する。

- フィルター: All repositories / All approvers / All requesters / 期間（Last week 等）/ All statuses
- リクエストの承認・却下を管理

## Dismissal requests > Secret scanning

> パス: `/orgs/{org}/security/closure-requests/secret-scanning`

Secret scanning アラートの dismissal リクエストを Organization 横断で表示・管理する。

- フィルター: All repositories / All approvers / All requesters / 期間（Last week 等）/ All statuses
- リクエストの承認・却下を管理

## Dismissal requests > Push protection bypass

> パス: `/orgs/{org}/security/bypass-requests/secret-scanning`

Push protection のバイパスリクエストを Organization 横断で表示・管理する [^15]。

- フィルター: All repositories / All approvers / All requesters / 期間（Last week 等）/ All statuses
- リクエストの承認・却下を管理

---

[^1]: [GitHub Docs: About security overview](https://docs.github.com/en/enterprise-cloud@latest/code-security/security-overview/about-security-overview)
[^2]: [GitHub Docs: Viewing security insights](https://docs.github.com/en/enterprise-cloud@latest/code-security/security-overview/viewing-security-insights)
[^3]: [GitHub Docs: Assessing the security risk of your code](https://docs.github.com/en/enterprise-cloud@latest/code-security/security-overview/assessing-code-security-risk)
[^4]: [GitHub Docs: Assessing adoption of security features](https://docs.github.com/en/enterprise-cloud@latest/code-security/security-overview/assessing-adoption-code-security)
[^5]: [GitHub Docs: About secret risk assessment](https://docs.github.com/en/enterprise-cloud@latest/code-security/securing-your-organization/understanding-your-organizations-exposure-to-leaked-secrets/about-secret-risk-assessment)
[^6]: [GitHub Docs: About security campaigns](https://docs.github.com/en/enterprise-cloud@latest/code-security/securing-your-organization/fixing-security-alerts-at-scale/about-security-campaigns)
[^7]: [GitHub Docs: Assessing adoption of security features - Enablement trends](https://docs.github.com/en/enterprise-cloud@latest/code-security/security-overview/assessing-adoption-code-security#viewing-enablement-trends-for-an-organization)
[^8]: [GitHub Docs: About code quality](https://docs.github.com/en/enterprise-cloud@latest/code-security/code-quality/about-code-quality)
[^9]: [GitHub Docs: Viewing metrics for pull request alerts](https://docs.github.com/en/enterprise-cloud@latest/code-security/security-overview/viewing-metrics-for-pull-request-alerts)
[^10]: [GitHub Docs: Viewing metrics for secret scanning push protection](https://docs.github.com/en/enterprise-cloud@latest/code-security/security-overview/viewing-metrics-for-secret-scanning-push-protection)
[^11]: [GitHub Docs: About Dependabot alerts](https://docs.github.com/en/enterprise-cloud@latest/code-security/dependabot/dependabot-alerts/about-dependabot-alerts)
[^12]: [GitHub Docs: About code scanning](https://docs.github.com/en/enterprise-cloud@latest/code-security/code-scanning/introduction-to-code-scanning/about-code-scanning)
[^13]: [GitHub Docs: About secret scanning](https://docs.github.com/en/enterprise-cloud@latest/code-security/secret-scanning/introduction/about-secret-scanning)
[^14]: [GitHub Docs: Responsible detection of generic secrets with AI](https://docs.github.com/en/enterprise-cloud@latest/code-security/secret-scanning/using-advanced-secret-scanning-and-push-protection-features/generic-secret-detection/responsible-ai-generic-secrets)
[^15]: [GitHub Docs: About delegated bypass for push protection](https://docs.github.com/en/enterprise-cloud@latest/code-security/secret-scanning/using-advanced-secret-scanning-and-push-protection-features/delegated-bypass-for-push-protection/about-delegated-bypass-for-push-protection)
