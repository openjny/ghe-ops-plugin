# Enterprise GitHub Connect

> パス: `/enterprises/{enterprise}/enterprise_installations`

## 概要

GitHub Connect は GHES（GitHub Enterprise Server）インスタンスと GHEC（GitHub Enterprise Cloud）を接続し、特定の機能やワークフローを共有する仕組み。接続は GHES 側から開始する必要がある。[^1]

## ナビゲーション

サブナビゲーションなし（単一ページ）。

## GitHub Connect

> パス: `/enterprises/{enterprise}/enterprise_installations`

- Enterprise Server 接続の一覧（接続がある場合）
- 接続がない場合: 「No Enterprise Server connections yet」メッセージと GHES 側からの接続手順へのリンク

### GitHub Connect で有効化できる機能

接続確立後、以下の機能を個別に有効化できる: [^2]

- **Automatic user license sync** — GHES と GHEC 間でユーザーライセンス使用状況を自動同期
- **Dependabot** — コード依存関係の脆弱性を検出・修正
- **GitHub.com actions** — GitHub.com のパブリックアクションをワークフローで利用可能にする
- **Server Statistics** — GHES の集約メトリクスを分析（GHE.com 接続時は利用不可）
- **Unified search** — GHEC リポジトリを GHES の検索結果に含める
- **Unified contributions** — GHES での作業を GHEC のコントリビューショングラフに匿名で反映

> GHE.com に接続する場合、Server Statistics と GitHub.com actions は利用不可。

---

[^1]: [GitHub Docs: About GitHub Connect](https://docs.github.com/en/enterprise-server@latest/admin/configuring-settings/configuring-github-connect/about-github-connect)
[^2]: [GitHub Docs: Enabling GitHub Connect for GHE.com](https://docs.github.com/en/enterprise-server@latest/admin/configuring-settings/configuring-github-connect/enabling-github-connect-for-ghecom)
