# Enterprise Insights

> パス: `/enterprises/{enterprise}/insights/copilot`

## 概要

Enterprise 全体の利用状況メトリクスダッシュボード。Copilot の利用状況、コード生成メトリクス、Actions の使用量・パフォーマンスメトリクスを確認できる。[^1]

## サブナビゲーション

| 項目 | パス |
|------|------|
| Copilot usage | `/enterprises/{enterprise}/insights/copilot` |
| Code generation | `/enterprises/{enterprise}/insights/copilot/code-generation` |
| Actions usage metrics | `/enterprises/{enterprise}/actions/metrics/usage` |
| Actions performance metrics | `/enterprises/{enterprise}/actions/metrics/performance` |

## セクション: Copilot usage

Copilot IDE の利用状況ダッシュボード。Copilot usage metrics が有効な場合にデータが表示される。

### 前提

AI Controls > Copilot > Metrics で「Copilot usage metrics」が有効である必要がある。
無効の場合: 「Copilot usage metrics are currently disabled」メッセージと有効化リンクが表示される。

### UI 要素

- フィードバックリンク: 「Give feedback」
- メトリクス管理リンク: 「Manage Copilot usage metrics」→ AI Controls > Copilot の Metrics セクションへ

## セクション: Code generation

Copilot によるコード生成のメトリクス。

## セクション: Actions usage metrics

> パス: `/enterprises/{enterprise}/actions/metrics/usage`

GitHub Actions の使用量メトリクス。

## セクション: Actions performance metrics

> パス: `/enterprises/{enterprise}/actions/metrics/performance`

GitHub Actions のパフォーマンスメトリクス。

---

[^1]: [GitHub Docs: About Copilot metrics](https://docs.github.com/en/copilot/concepts/copilot-metrics)
