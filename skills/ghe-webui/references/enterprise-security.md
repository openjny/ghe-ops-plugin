# Enterprise Security and quality

> パス: `/enterprises/{enterprise}/security/overview`

## 概要

Enterprise 全体のセキュリティアラートのトレンド、リスク分析、セキュリティ機能のカバレッジ、各種セキュリティ機能の有効化状況を一元的に確認するダッシュボード。[^1]

## サイドナビゲーション

| 項目 | パス | 備考 |
|------|------|------|
| Overview | `/enterprises/{enterprise}/security/overview` | アラートトレンド |
| Risk | `/enterprises/{enterprise}/security/risk` | リスク分析 |
| Coverage | `/enterprises/{enterprise}/security/coverage` | カバレッジ状況 |
| **Insights** | | |
| ↳ Enablement | `/enterprises/{enterprise}/security/metrics/enablement` | 機能有効化率 |
| ↳ CodeQL pull requests | `/enterprises/{enterprise}/security/metrics/codeql` | CodeQL PR メトリクス |
| ↳ Secret scanning | `/enterprises/{enterprise}/security/metrics/secret-scanning` | シークレットスキャンメトリクス |
| **Findings** | | |
| ↳ Dependabot | (展開可能なサブメニュー) | |
| ↳ Code scanning | `/enterprises/{enterprise}/security/alerts/code-scanning` | |
| ↳ Secret scanning | `/enterprises/{enterprise}/security/alerts/secret-scanning` | |
| **Dismissal requests** | | |
| ↳ Dependabot | `/enterprises/{enterprise}/security/dismissal-requests/dependabot` | |
| ↳ Code scanning | `/enterprises/{enterprise}/security/dismissal-requests/code-scanning` | |
| ↳ Secret scanning | `/enterprises/{enterprise}/security/dismissal-requests/secret-scanning` | |
| ↳ Push protection bypass | `/enterprises/{enterprise}/security/bypass-requests/secret-scanning` | |

## セクション: Overview

### UI 要素

- フィルタ: Advanced filter（`archived:false tool:github` 等のクエリ構文）
- 期間選択: 「Choose period...」ドロップダウン（Last 30 days 等）
- フィードバックリンク: 「Give feedback」

---

[^1]: [GitHub Docs: About security overview](https://docs.github.com/enterprise-cloud@latest/code-security/security-overview/about-security-overview)
