---
name: github-waf
description: "GitHub Well-Architected Framework (WAF) に基づいた、ベストプラクティス・設計原則・チェックリスト・推奨事項を提供するスキル。Use when: GitHub Enterprise の設計、ガバナンス設定、生産性向上、コラボレーション改善。Triggers: GitHub, GitHub Enterprise, Well-Architected Framework, 設計原則, セキュリティレビュー, ガバナンス, アーキテクチャレビュー, Copilot 導入"
argument-hint: "ピラー名 or トピック (例: productivity, security, governance)"
---

# GitHub Well-Architected Framework

GitHub Enterprise の管理・運用における設計原則、チェックリスト、推奨事項を体系的に提供する。
ソース: https://wellarchitected.github.com/library/overview/

## When to Use

- GitHub Enterprise の設計レビュー・アセスメント
- 新規 GitHub Enterprise 環境の設計
- 既存環境の改善点の特定
- セキュリティポスチャの評価
- ガバナンスポリシーの策定
- CI/CD パイプラインの設計・改善
- Copilot の大規模導入計画
- リポジトリ管理の最適化

## Framework Structure

GitHub Well-Architected は 4 つのレイヤーで構成される:

1. **Pillars** — 5 つの重点領域
2. **Design Principles** — 各ピラーの設計原則（Start → Mature → Advance の成熟度モデル）
3. **Checklists** — 評価用チェックリスト
4. **Recommendations** — シナリオベースの具体的推奨事項

## Five Pillars

| Pillar | Focus | Design Principles |
|--------|-------|-------------------|
| ⚙️ Productivity | 開発ワークフローの速度と効率 | Automation, Integration, Continuous Learning, Feedback, Engineering System Success, Keep it Simple |
| 👥 Collaboration | チームワークを強化するツールとプラクティス | Effective Communication, Inclusivity, Openness, Transparency, Flexibility, Keep it Simple |
| 🔒 Application Security | アプリケーションのセキュリティ確保 | Security, Compliance, Proactivity, Awareness, Keep it Simple |
| 📜 Governance | ポリシーとコンプライアンスに沿った管理・監督 | Auditability, Accountability, Adaptability, Control, Keep it Simple |
| 📐 Architecture | 技術設計とデプロイの構造 | Scalability, Resiliency, Efficiency, Disaster Recovery, Modularity, Interoperability, Observability, Keep it Simple |

## Procedure

### Step 1: 対象ピラーの特定

ユーザーの質問・課題に応じて、関連するピラーを特定する。複数ピラーにまたがる場合もある。

### Step 2: 設計原則の確認

該当ピラーのリファレンスファイルを読み込み、設計原則（Design Principles）を確認する:

- [Productivity 詳細](./references/pillar-productivity.md)
- [Collaboration 詳細](./references/pillar-collaboration.md)
- [Application Security 詳細](./references/pillar-application-security.md)
- [Governance 詳細](./references/pillar-governance.md)
- [Architecture 詳細](./references/pillar-architecture.md)

各設計原則は **Start → Mature → Advance** の成熟度モデルに沿って構成されている。

### Step 3: チェックリストによる評価

各ピラーのリファレンスに含まれるチェックリストを使って現状を評価する。

### Step 4: 推奨事項の適用

シナリオに応じた推奨事項を参照する:

- [シナリオ・推奨事項](./references/scenarios-and-recommendations.md)

### Step 5: アンチパターンの回避

- [アンチパターン一覧](./references/anti-patterns.md)

## Quick Reference: Key Recommendations by Topic

### Copilot 導入
- 計画的なローンチ（Pre-launch → Launch → Post-launch フェーズ）
- 複数チャネルでのコミュニケーション
- エグゼクティブスポンサーシップ
- インストラクター主導 + オンデマンド学習
- 内部コミュニティ（Expert Hub）構築
- PRU（Premium Request Units）のバジェット管理
- 詳細 → Productivity リファレンス / Governance リファレンス

### GitHub Actions セキュリティ
- OIDC 認証（長寿命クレデンシャル排除）
- アクションの SHA ピンニング
- least privilege パーミッション（デフォルト read-only）
- `pull_request_target` の回避
- self-hosted runner はパブリックリポジトリに使わない
- 詳細 → Application Security リファレンス

### リポジトリ管理
- カスタムプロパティによるメタデータ管理
- リポジトリルールセットによるポリシー強制
- Security Configurations による一括セキュリティ設定
- CODEOWNERS による所有権定義
- 詳細 → Governance リファレンス

### エンジニアリングシステムメトリクス
- 4 ゾーン: Quality, Velocity, Developer Happiness, Business Outcomes
- 各ゾーン 3 つの主要メトリクス（計 12 メトリクス）
- リーディング指標とラギング指標のバランス
- 詳細 → Productivity リファレンス

### セキュリティ対策
- 開発者ワークスペースのセキュリティ（Dev Container, Codespaces）
- 依存関係サプライチェーン攻撃への防御（6 層防御）
- セキュリティアラートの優先順位付け（EPSS, カスタムプロパティ活用）
- GHAS（GitHub Advanced Security）の大規模展開
- リポジトリ脅威モデル
- NIST SSDF 準拠
- 詳細 → Application Security リファレンス

### Enterprise ポリシー
- Actions 実行の制限（GitHub + Verified Creator のみ）
- ワークフロートークンのデフォルト read-only
- PR 自動承認の無効化
- フォークの無効化
- リポジトリ可視性変更の制限
- PAT の承認フロー
- Webhook の SSL + シークレット設定
- 監査ログストリーミング
- 詳細 → Governance リファレンス

## Assessment Process

1. **Initial Review** — 5 ピラーに基づく環境レビュー
2. **Interviews and Surveys** — ステークホルダーへのヒアリング
3. **Analysis and Scoring** — ピラー・原則に対するスコアリング
4. **Recommendations** — 改善提案レポート

## Source

- [GitHub Well-Architected Content Library](https://wellarchitected.github.com/library/overview/)
- [GitHub Docs](https://docs.github.com/)
- [GitHub Resources](https://resources.github.com/)
