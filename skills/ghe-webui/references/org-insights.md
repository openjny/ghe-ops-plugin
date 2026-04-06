# Organization Insights

> パス: `/orgs/{org}/insights`

## 概要

Organization の利用状況・パフォーマンスメトリクスダッシュボード。Copilot の利用状況・コード生成メトリクス、Actions の使用量・パフォーマンスメトリクス、REST API の利用状況を確認できる。[^1] [^2] [^3]

## ナビゲーション

| 項目 | パス |
|------|------|
| Copilot usage | `/orgs/{org}/insights/copilot/usage` |
| Code generation | `/orgs/{org}/insights/copilot/code-generation` |
| Actions Usage Metrics | `/orgs/{org}/actions/metrics/usage` |
| Actions Performance Metrics | `/orgs/{org}/actions/metrics/performance` |
| REST API | `/orgs/{org}/insights/api` |

## Copilot usage

> パス: `/orgs/{org}/insights/copilot/usage`
>
> 注: ページタイトルは「Copilot IDE usage」

Copilot IDE の利用状況ダッシュボード。Organization 内の Copilot 利用トレンドを可視化する。Copilot usage metrics が有効な場合にデータが表示される。[^4]

### 前提

Enterprise の AI Controls > Copilot > Metrics で「Copilot usage metrics」が有効である必要がある。
無効の場合: 「Copilot usage metrics are currently disabled」メッセージと有効化リンクが表示される。

### できること

- Organization 内の Copilot 採用状況・利用トレンドの確認
- フィードバック送信: 「Give feedback」リンク
- メトリクス管理: 「Manage Copilot usage metrics」→ Enterprise の AI Controls > Copilot の Metrics セクション (`/enterprises/{enterprise}/ai-controls/copilot#metrics`) へ遷移

## Code generation

> パス: `/orgs/{org}/insights/copilot/code-generation`
>
> 注: ページタイトルは「IDE code generation」

Copilot によるコード生成メトリクスダッシュボード。ユーザーとエージェントによるコード生成アクティビティを Organization レベルで表示する。[^4]

### 前提

Copilot usage と同じく「Copilot usage metrics」が有効である必要がある。

### できること

- AI によって変更されたコード行数の確認
- ユーザー主導のコード変更: コンプリーションやチャットアクションを通じたコード提案・手動追加の行数
- エージェント主導のコード変更: edit / agent / custom モードでエージェントが自動追加・削除した行数
- モデル別・言語別のアクティビティ内訳
- フィードバック送信: 「Give feedback」リンク
- メトリクス管理: 「Manage Copilot usage metrics」→ Enterprise の AI Controls > Copilot の Metrics セクションへ遷移

## Actions Usage Metrics

> パス: `/orgs/{org}/actions/metrics/usage`

GitHub Actions の使用量メトリクス。Organization 内のワークフロー分数・ジョブ実行数を追跡する。[^1]

### サマリーカード

- **Total minutes**: Organization 全体の合計実行分数
- **Total job runs**: Organization 全体の合計ジョブ実行数

### タブ

| タブ | 内容 |
|------|------|
| Workflows | ワークフロー別の使用量データ |
| Jobs | ジョブ別の使用量データ |
| Repositories | リポジトリ別の使用量データ |
| Runtime OS | ランタイム OS 別の使用量データ |
| Runner type | ランナータイプ（self-hosted / GitHub-hosted）別の使用量データ |

### できること

- 期間選択: Current week / Current month / Last month / Last 30 days / Last 90 days / Last year / Custom
- フィルター: 各タブでフィルター条件を追加してデータを絞り込み
- レポートダウンロード: CSV 形式でダウンロード（「Download report」ボタン）

## Actions Performance Metrics

> パス: `/orgs/{org}/actions/metrics/performance`

GitHub Actions のパフォーマンスメトリクス。Organization 内のワークフロー・ジョブの実行効率と信頼性を追跡する。[^1]

### サマリーカード

- **Avg job run time**: Organization 内ジョブの平均実行時間
- **Avg job queue time**: Organization 内ジョブの平均キュー待ち時間
- **Job failure rate**: Organization 内ジョブの失敗率
- **Failed job usage**: 失敗ジョブに費やされた合計分数

### タブ

| タブ | 内容 |
|------|------|
| Workflows | ワークフロー別のパフォーマンスデータ |
| Jobs | ジョブ別のパフォーマンスデータ |
| Repositories | リポジトリ別のパフォーマンスデータ |
| Runtime OS | ランタイム OS 別のパフォーマンスデータ |
| Runner type | ランナータイプ別のパフォーマンスデータ |

### できること

- 期間選択: Actions Usage Metrics と同じ期間選択が可能
- フィルター: 各タブでフィルター条件を追加してデータを絞り込み
- レポートダウンロード: CSV 形式でダウンロード（「Download report」ボタン）

## REST API

> パス: `/orgs/{org}/insights/api`

Organization 内の REST API リクエスト数とレート制限の状況を可視化する。アプリやユーザーごとのリクエスト量を確認できる。[^3]

### サマリーカード

- **Total REST requests**: 選択期間内の REST API リクエスト合計数
- **Primary-rate-limited requests**: 選択期間内にプライマリレート制限を受けたリクエスト数

### チャート

- 選択期間内の REST API リクエスト数の時系列グラフ

### Actors テーブル

- アプリやユーザーごとの REST API 使用量の一覧
- 名前検索: アプリまたはユーザー名での検索
- タイプフィルター: All / App / User
- リクエストフィルター: All / Primary-rate-limited
- 個別のアクターを選択してアクセスした API エンドポイントの詳細を表示

### できること

- 期間選択: Last 30 minutes / Last 1 hour / Last 3 hours / Last 12 hours / Last 24 hours（デフォルト） / Last 7 days / Last 31 days / Custom
- インターバル選択: 時系列グラフの粒度（1 hour 等）を変更
- タイムゾーン切替: UTC / Local（ブラウザのタイムゾーン）
- アクター別のドリルダウン: ユーザーの場合は PAT や OAuth アプリごとの内訳も確認可能

---

[^1]: [GitHub Docs: Viewing GitHub Actions metrics for your organization](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/viewing-github-actions-metrics-for-your-organization)
[^2]: [GitHub Docs: Viewing insights for dependencies in your organization](https://docs.github.com/en/enterprise-cloud@latest/organizations/collaborating-with-groups-in-organizations/viewing-insights-for-dependencies-in-your-organization)
[^3]: [GitHub Docs: Viewing API insights in your organization](https://docs.github.com/en/enterprise-cloud@latest/organizations/managing-programmatic-access-to-your-organization/viewing-api-insights-in-your-organization)
[^4]: [GitHub Docs: Tracking license activation and initial usage with Copilot usage metrics](https://docs.github.com/en/copilot/rolling-out-github-copilot-at-scale/analyzing-usage-over-time-with-the-copilot-metrics-api)
