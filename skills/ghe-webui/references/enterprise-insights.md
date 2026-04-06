# Enterprise Insights

> パス: `/enterprises/{enterprise}/insights/copilot`

## 概要

Enterprise 全体の利用状況メトリクスダッシュボード。Copilot の利用状況・コード生成メトリクス、Actions の使用量・パフォーマンスメトリクスを確認できる。[^1] [^2]

## ナビゲーション

| 項目 | パス |
|------|------|
| Copilot usage | `/enterprises/{enterprise}/insights/copilot` |
| Code generation | `/enterprises/{enterprise}/insights/copilot/code-generation` |
| Actions usage metrics | `/enterprises/{enterprise}/actions/metrics/usage` |
| Actions performance metrics | `/enterprises/{enterprise}/actions/metrics/performance` |

## Copilot usage

> パス: `/enterprises/{enterprise}/insights/copilot`
>
> ※ ページタイトルは「Copilot IDE usage」

Copilot IDE の利用状況ダッシュボード。28 日間の利用トレンドを可視化する。Copilot usage metrics が有効な場合にデータが表示される。[^3]

### 前提

AI Controls > Copilot > Metrics で「Copilot usage metrics」が有効である必要がある。
無効の場合: 「Copilot usage metrics are currently disabled」メッセージと有効化リンクが表示される。

### できること

- Copilot の採用状況・利用トレンドの確認
- フィードバック送信: 「Give feedback」リンク
- メトリクス管理: 「Manage Copilot usage metrics」→ AI Controls > Copilot の Metrics セクション (`/enterprises/{enterprise}/ai-controls/copilot#metrics`) へ遷移

## Code generation

> パス: `/enterprises/{enterprise}/insights/copilot/code-generation`
>
> ※ ページタイトルは「IDE code generation」

Copilot によるコード生成メトリクスダッシュボード。ユーザーとエージェントによるコード生成アクティビティを表示する。[^4]

### 前提

Copilot usage と同じく「Copilot usage metrics」が有効である必要がある。

### できること

- AI によって変更されたコード行数（Lines of code changed with AI）の確認
- ユーザー主導のコード変更: コンプリーションやチャットアクションを通じたコード提案・手動追加の行数
- エージェント主導のコード変更: edit / agent / custom モードでエージェントが自動追加・削除した行数
- モデル別・言語別のアクティビティ内訳
- フィードバック送信: 「Give feedback」リンク
- メトリクス管理: 「Manage Copilot usage metrics」→ AI Controls > Copilot の Metrics セクションへ遷移

## Actions usage metrics

> パス: `/enterprises/{enterprise}/actions/metrics/usage`
>
> ※ ページタイトルは「Actions Usage Metrics」

GitHub Actions の使用量メトリクス。Enterprise 全体のワークフロー分数・ジョブ実行数を追跡する。[^5]

### サマリーカード

- **Total minutes**: Enterprise 全体の合計実行分数
- **Total job runs**: Enterprise 全体の合計ジョブ実行数

### タブ

| タブ | 内容 |
|------|------|
| Workflows | ワークフロー別の使用量データ |
| Jobs | ジョブ別の使用量データ |
| Organizations | Organization 別の使用量データ |
| Repositories | リポジトリ別の使用量データ |
| Runtime OS | ランタイム OS 別の使用量データ |
| Runner type | ランナータイプ（self-hosted / GitHub-hosted）別の使用量データ |

### できること

- 期間選択: Current week / Current month / Last month / Last 30 days / Last 90 days / Last year / Custom
- フィルター: Advanced filter によるデータ絞り込み
- レポートダウンロード: CSV 形式でエクスポート

## Actions performance metrics

> パス: `/enterprises/{enterprise}/actions/metrics/performance`
>
> ※ ページタイトルは「Actions Performance Metrics」

GitHub Actions のパフォーマンスメトリクス。ワークフローの効率性と信頼性を分析する。[^5]

### サマリーカード

- **Avg job run time**: ジョブの平均実行時間
- **Avg job queue time**: ジョブの平均キュー待ち時間
- **Job failure rate**: ジョブの失敗率
- **Failed job usage**: 失敗したジョブで消費された合計分数

### タブ

| タブ | 内容 |
|------|------|
| Workflows | ワークフロー別のパフォーマンスデータ |
| Jobs | ジョブ別のパフォーマンスデータ |
| Organizations | Organization 別のパフォーマンスデータ |
| Repositories | リポジトリ別のパフォーマンスデータ |
| Runtime OS | ランタイム OS 別のパフォーマンスデータ |
| Runner type | ランナータイプ別のパフォーマンスデータ |

### できること

- 期間選択: Current week / Current month / Last month / Last 30 days / Last 90 days / Last year / Custom
- フィルター: Advanced filter によるデータ絞り込み
- レポートダウンロード: CSV 形式でエクスポート

---

[^1]: [GitHub Docs: GitHub Copilot usage metrics](https://docs.github.com/en/copilot/concepts/copilot-usage-metrics/copilot-metrics)
[^2]: [GitHub Docs: About GitHub Actions metrics](https://docs.github.com/en/actions/concepts/about-github-actions-metrics)
[^3]: [GitHub Docs: Viewing the Copilot usage metrics dashboard](https://docs.github.com/en/copilot/how-tos/administer-copilot/view-usage-and-adoption)
[^4]: [GitHub Docs: Viewing the code generation dashboard](https://docs.github.com/en/copilot/how-tos/administer-copilot/view-code-generation)
[^5]: [GitHub Docs: Viewing GitHub Actions metrics](https://docs.github.com/en/actions/administering-github-actions/viewing-github-actions-metrics-for-your-organization)
